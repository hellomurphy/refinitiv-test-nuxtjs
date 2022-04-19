<template>
  <div class="flex">
    <div class="flex-1 w-200 bg-red-200">
      <input
        type="number"
        id="number"
        name="number"
        v-model="number"
        class="
          w-1-2
          mx-auto
          shadow
          appearance-none
          border
          rounded
          text-gray-700
          leading-tight
        "
        @blur="checkIsInteger(), checkNumber(typeCheck)"
      />
    </div>
    <div class="flex-1 w-100 bg-blue-200">
      <select @click="(event) => checkNumber(event.target.value)">
        <option value=""></option>
        <option value="isPrime">IsPrime</option>
        <option value="isFibonacci">IsFibonacci</option>
      </select>
    </div>
    <div class="flex-1 w-300 bg-green-200">{{ result }}</div>
  </div>
</template>

<script>
export default {
  data() {
    return { number: 0, typeCheck: '', result: '' }
  },
  methods: {
    checkNumber(typeCheck) {
      if (typeCheck === 'isPrime') {
        this.typeCheck = 'isPrime'
        const checkIsPrime = () => {
          if (this.number === 1) return false
          for (let i = 2; i < this.number; i++) {
            if (this.number % i === 0) {
              return false
            }
          }
          return true
        }
        checkIsPrime() === true
          ? (this.result = 'true')
          : (this.result = 'false')
      } else if (typeCheck === 'isFibonacci') {
        this.typeCheck = 'isFibonacci'
        const isPerfectSquare = (x) => {
          const s = parseInt(Math.sqrt(x))
          return s * s === x
        }
        const checkIsFibonacci = () => {
          return (
            isPerfectSquare(5 * this.number * this.number + 4) ||
            isPerfectSquare(5 * this.number * this.number - 4)
          )
        }
        checkIsFibonacci() ? (this.result = 'true') : (this.result = 'false')
      } else {
        this.result = ''
      }
    },
    checkIsInteger() {
      if (this.number < 0) {
        this.number = 1
      }
      if (!Number.isInteger(this.number)) {
        this.number = Math.round(this.number)
      }
    },
  },
}
</script>
