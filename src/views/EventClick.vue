<template>
    <div>
        <button v-on:click="increaseCounter">Add 1</button>
        <p>Counter is :{{ counter }}</p>
        <button v-on:click="increaseCounter2(3)">increas</button>
        <button v-on:click="one(), two()">다중호출</button>
        <select v-model="city" @change="changeSelect">
            <option value="1">서울</option>
            <option value="2">부산</option>
            <option value="3">제주</option>
        </select>
    </div>
</template>

<script>
export default {
    data() {
        return {
            counter: 5,
            city: 1
        }
    },
    methods: {
        increaseCounter() {
            console.log('increaseCounter')
            this.counter = this.counter + parseInt(this.city);
            //this.city = this.city+1;
        },
        increaseCounter2(num) {
            this.counter = this.counter + num;
            this.city = this.city + num;
        },
        one() {
            alert('one')
        },
        two() {
            alert('two')
        },
        changeSelect() {
            switch (this.city) {
                case '1':
                    console.log('서울을 선택했습니다.');
                    break;
                case '2':
                    console.log('부산을 선택했습니다.');
                    break;
                case '3':
                    console.log('제주를 선택했습니다.');
                    break;
                default:
                    console.log('알 수 없는 도시를 선택했습니다.');
            }
        }
    },
    beforeUpdate() {
        //변경 이전에 필요처리를 구현.
        console.log('beforeUpdate')
    },
    updated() {
        //변경 이후에 필요한 처리를 구현.
        console.log('updated')
    }
}
</script>