<template>
    <div class="calc">
        <div class="display">{{result || 0}}</div>
        <div class="btn" @click="clear">C</div>
        <div class="btn pi" @click="pi"><span>&#960;</span></div>
        <div class="btn">&radic;</div>
        <div class="btn operator" @click="divide">&#8725;</div>
        <div class="btn" @click="append(7)">7</div>
        <div class="btn" @click="append(8)">8</div>
        <div class="btn" @click="append(9)">9</div>
        <div class="btn operator" @click="multiply">&times;</div>
        <div class="btn" @click="append(4)">4</div>
        <div class="btn" @click="append(5)">5</div>
        <div class="btn" @click="append(6)">6</div>
        <div class="btn operator" @click="subtract">&minus;</div>
        <div class="btn" @click="append(1)">1</div>
        <div class="btn" @click="append(2)">2</div>
        <div class="btn" @click="append(3)">3</div>
        <div class="btn operator" @click="sum">&#43;</div>
        <div class="btn">M</div>
        <div class="btn" @click="append(0)">0</div>
        <div class="btn dot" @click="dot"><span>&#46;</span></div>
        <div class="btn equal" @click="equal">=</div>
    </div>
</template>

<script>
export default {
    data(){
        return {
            result: '',
            prev: null,
            operator: null,
            operatorClick: false
        }
    },
    methods: {
        clear(){
            this.result = ''
        },
        pi(){
            if(this.operatorClick) {
                this.result = '';
                this.operatorClick = false;
            }
            this.result = this.result + Math.PI;
        },
        append(number){
            if(this.operatorClick) {
                this.result = '';
                this.operatorClick = false;
            }
            this.result = this.result + number;
        },
        dot(){
            if(this.result.indexOf('.') === -1) {
                this.append('.');
            }
        },
        divide(){
            this.operator = (a,b) => b/a;
            this.setPrev();
        },
        multiply(){
            this.operator = (a,b) => a*b;
            this.setPrev();
        },
        subtract(){
            this.operator = (a,b) => b-a;
            this.setPrev();
        },
        sum(){
            this.operator = (a,b) => a+b;
            this.setPrev();
        },
        equal(){
            this.result = this.operator(
                parseFloat(this.result),
                parseFloat(this.prev)
            );
            this.prev = null;
        },
        setPrev(){
            this.prev = this.result;
            this.operatorClick = true;
        }
    }
}

</script>

<style lang="scss">
.calc {
    font-size: 2em;
    padding: 84px 16px 24px 16px;
    width: 250px;
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
    margin: 0 auto;
    background: rgba(80,80,80,1);
    background: -moz-linear-gradient(top, rgba(80,80,80,1) 0%, rgba(55,55,55,1) 100%);
    background: -webkit-gradient(left top, left bottom, color-stop(0%, rgba(80,80,80,1)), color-stop(100%, rgba(55,55,55,1)));
    background: -webkit-linear-gradient(top, rgba(80,80,80,1) 0%, rgba(55,55,55,1) 100%);
    background: -o-linear-gradient(top, rgba(80,80,80,1) 0%, rgba(55,55,55,1) 100%);
    background: -ms-linear-gradient(top, rgba(80,80,80,1) 0%, rgba(55,55,55,1) 100%);
    background: linear-gradient(to bottom, rgba(80,80,80,1) 0%, rgba(55,55,55,1) 100%);
    filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#505050', endColorstr='#373737', GradientType=0 );
    border-radius: 16px;
    justify-content: center;
    box-shadow: 8px 8px 14px rgba(80,80,80,.5), 3px 3px 6px rgba(80,80,80,.7);
    -webkit-box-shadow: 8px 8px 14px rgba(80,80,80,.5), 3px 3px 6px rgba(80,80,80,.7);
    -moz-box-shadow: 8px 8px 14px rgba(80,80,80,.5), 3px 3px 6px rgba(80,80,80,.7);
    -o-box-shadow: 8px 8px 14px rgba(80,80,80,.5), 3px 3px 6px rgba(80,80,80,.7);



    .display {
        grid-column-start: span 4;
        text-align: right;
        padding-bottom: 8px;
        margin: 0 16px 16px 16px;
        font-size: 1.3em;
        color: #fff;
        border-bottom: .5px solid #848484;
        overflow: hidden;
        -moz-user-select: none; /* Firefox */
        -ms-user-select: none; /* Internet Explorer */
        -khtml-user-select: none; /* KHTML browsers (e.g. Konqueror) */
        -webkit-user-select: none; /* Chrome, Safari, and Opera */
        -webkit-touch-callout: none; /* Disable Android and iOS callouts*/
    }

    .btn {
        display: flex;
        justify-content: center;
        align-items: center;
        color: #dddddd;
        width: 60px;
        height: 60px;
        font-size: .5em;
        cursor: pointer;
        -moz-user-select: none; /* Firefox */
        -ms-user-select: none; /* Internet Explorer */
        -khtml-user-select: none; /* KHTML browsers (e.g. Konqueror) */
        -webkit-user-select: none; /* Chrome, Safari, and Opera */
        -webkit-touch-callout: none; /* Disable Android and iOS callouts*/
        -webkit-tap-highlight-color:  rgba(255, 255, 255, 0); /* Removes higlight on click event on touch devices */
        border-radius: 50%;

        &:active {
            background-color: #373737;
        }
    }

    .operator {
        color: #FE6F6F;
        font-size: .7em;
    }

    .equal {
        width: 32px;
        height: 32px;
        border-radius: 50%;
        background-color: #FE6F6F;
        color: #fff;
        margin: auto;
        
        &:active {
            background-color: #FE6F6F;
            box-shadow: 0 0 10px #FE6F6F;
        }
    }

    .pi {
        font-size: .6em;

        span {
            padding-bottom: 3px;
        }
    }

    .dot {
        font-size: .7em;

        span {
            padding-bottom: 4px;
        }
    }
}
</style>