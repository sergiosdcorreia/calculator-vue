<template>
    <div class="calc">
        <div class="display">123456789</div>
        <div class="btn">C</div>
        <div class="btn pi"><span>&#8508;</span></div>
        <div class="btn">&radic;</div>
        <div class="btn operator">&#8725;</div>
        <div class="btn">7</div>
        <div class="btn">8</div>
        <div class="btn">9</div>
        <div class="btn operator">&times;</div>
        <div class="btn">4</div>
        <div class="btn">5</div>
        <div class="btn">6</div>
        <div class="btn operator">&minus;</div>
        <div class="btn">1</div>
        <div class="btn">2</div>
        <div class="btn">3</div>
        <div class="btn operator">&#43;</div>
        <div class="btn">M</div>
        <div class="btn">0</div>
        <div class="btn">&#46;</div>
        <div class="btn equal">=</div>
    </div>
</template>

<script>
export default {
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

    .display {
        grid-column-start: span 4;
        text-align: right;
        padding-bottom: 8px;
        margin: 0 16px 16px 16px;
        font-size: 1.3em;
        color: #fff;
        border-bottom: .3px solid #848484;
    }

    .btn {
        display: flex;
        justify-content: center;
        align-items: center;
        color: #dddddd;
        height: 50px;
        font-size: .5em;
        cursor: pointer;

        &:active {
            background-color: #353535;
        }
    }

    .operator {
        color: #FE6F6F;
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
        font-size: .8em;

        span {
            padding-bottom: 6px;
        }
    }
}
</style>