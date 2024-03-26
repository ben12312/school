<template>
    <vue-advanced-chat
        :current-user-id="currentUserId"
        :rooms="JSON.stringify(rooms)"
        :rooms-loaded="true"
        :messages="JSON.stringify(messages)"
        :room-actions="JSON.stringify(roomActions)"
        @send-message="sendMessage($event.detail[0])"
        @fetch-messages="fetchMessages($event.detail[0])"/>
</template>

<script>
import { register } from 'vue-advanced-chat'
register()

// Or if you used CDN import
// window['vue-advanced-chat'].register()

export default {
    data() {
        return {
            currentUserId: '1234',
            rooms: [
                {
                    roomId: '1',
                    roomName: 'Room 1',
                    avatar: 'https://66.media.tumblr.com/avatar_c6a8eae4303e_512.pnj',
                    users: [
                        { _id: '1234', username: 'John Doe' },
                        { _id: '4321', username: 'John Snow' }
                    ]
                }
            ],
            messages: [
                {
                    _id: 121,
                    indexId: 12092,
                    content: 'Message 1',
                    senderId: '1234',
                    username: 'John Doe',
                    avatar: 'https://66.media.tumblr.com/avatar_c6a8eae4303e_512.pnj',
                    date: '13 November 2023',
                    timestamp: '10:20',
                    // system: false,
                    // saved: true,
                    // distributed: true,
                    // seen: true,
                    // deleted: false,
                    // failure: true,
                    // disableActions: false,
                    // disableReactions: false,
                    // files: [
                    //     {
                    //         name: 'My File',
                    //         size: 67351,
                    //         type: 'png',
                    //         audio: true,
                    //         duration: 14.4,
                    //         url: 'https://firebasestorage.googleapis.com/...',
                    //         preview: 'https://c4.wallpaperflare.com/wallpaper/603/383/734/car-vehicle-render-digital-art-bmw-hd-wallpaper-preview.jpg',
                    //         progress: 88
                    //     }
                    // ],
                    // reactions: {
                    //     "😁": [
                    //         '1234', // USER_ID
                    //         '4321'
                    //     ],
                    //     "🥰": [
                    //         '1234'
                    //     ]
                    // },
                    // replyMessage: {
                    //     content: 'Reply Message',
                    //     senderId: '4321',
                    //     files: [
                    //         {
                    //             name: 'My Replied File',
                    //             size: 67351,
                    //             type: 'png',
                    //             audio: true,
                    //             duration: 14.4,
                    //             url: 'https://v3.router.vuejs.org/',
                    //             preview: 'https://c4.wallpaperflare.com/wallpaper/603/383/734/car-vehicle-render-digital-art-bmw-hd-wallpaper-preview.jpg'
                    //         }
                    //     ]
                    // },
                }
            ],
            roomActions: [
                { name: 'inviteUser', title: 'Invite User' },
                { name: 'removeUser', title: 'Remove User' },
                { name: 'deleteRoom', title: 'Delete Room' }
            ]
        }
    },
    methods: {
        fetchMessages({ options = {} }) {
            setTimeout(() => {
                if (options.reset) {
                    this.messages = this.addMessages(true)
                } else {
                    this.messages = [...this.addMessages(), ...this.messages]
                    this.messagesLoaded = true
                }
                // this.addNewMessage()
            })
        },

        addMessages(reset) {
            const messages = []
            for (let i = 0; i < 30; i++) {
                messages.push({
                    _id: reset ? i : this.messages.length + i,
                    content: `${reset ? '' : 'paginated'} message ${i + 1}`,
                    avatar: 'https://66.media.tumblr.com/avatar_c6a8eae4303e_512.pnj',
                    senderId: '4321',
                    username: 'John Doe',
                    date: '13 November 2023',
                    timestamp: '10:20'
                })
            }
            return messages
        },

        sendMessage(message) {
            this.messages = [
                ...this.messages,
                {
                    _id: this.messages.length,
                    content: message.content,
                    senderId: this.currentUserId,
                    avatar: `https://c4.wallpaperflare.com/wallpaper/603/383/734/car-vehicle-render-digital-art-bmw-hd-wallpaper-preview.jpg`,
                    timestamp: new Date().toString().substring(16, 21),
                    date: new Date().toDateString()
                }
            ]
        },

        addNewMessage() {
            setTimeout(() => {
                this.messages = [
                    ...this.messages,
                    {
                        _id: this.messages.length,
                        content: 'NEW MESSAGE',
                        senderId: '1234',
                        timestamp: new Date().toString().substring(16, 21),
                        date: new Date().toDateString()
                    }
                ]
            }, 2000)
        }
    },
}
</script>