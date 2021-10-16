<template >
    <!-- container -->
    <main class="min-h-screen w-full grid place-content-center" onmousedown="return false;">
        <!-- calculator -->
        <div class="max-w-md mx-auto bg-gray-200 p-4 h-full rounded-lg" onmousedown="return false;">
            <!-- output -->
            <div
                class="bg-white rounded-sm p-2 border-2 border-gray-300"
                onmousedown="return false;"
            >
                <p class="text-5xl mt-5 text-blue-700 break-words text-right">{{ total }}</p>

                <input
                    type="text"
                    ref="output"
                    class="w-full text-3xl text-right text-gray-500 resize-none mt-5 focus:outline-none bg-transparent"
                    placeholder="0"
                    autofocus
                />
            </div>

            <!-- buttons -->
            <div
                class="text-3xl grid align-middle grid-cols-4 gap-2 mt-2"
                style="min-height: 60vh"
                onmousedown="return false;"
            >
                <!-- -1 row -->
                <button
                    class="grid place-items-center text-4xl text-blue-700 bg-white rounded-sm active:bg-gray-800 border-2 border-gray-300 transtion"
                    onmousedown="return false"
                >
                    <svg
                        class="w-6 h-6 font-semibold"
                        fill="none"
                        stroke="currentColor"
                        viewBox="0 0 24 24"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M5 12h.01M12 12h.01M19 12h.01M6 12a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0zm7 0a1 1 0 11-2 0 1 1 0 012 0z"
                        />
                    </svg>
                </button>

                <input
                    type="button"
                    value="^"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm text-blue-700 font-semibold border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="%"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm text-blue-700 font-semibold border-2 border-gray-300 hover:bg-gray-100"
                />

                <button
                    class="grid place-items-center text-blue-700 bg-white rounded-sm border-2 border-gray-300 hover:bg-gray-100"
                    @click="back"
                    onmousedown="return false"
                >
                    <svg
                        class="w-10 h-10"
                        fill="none"
                        stroke="currentColor"
                        viewBox="0 0 24 24"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <path
                            stroke-linecap="round"
                            stroke-linejoin="round"
                            stroke-width="2"
                            d="M12 14l2-2m0 0l2-2m-2 2l-2-2m2 2l2 2M3 12l6.414 6.414a2 2 0 001.414.586H19a2 2 0 002-2V7a2 2 0 00-2-2h-8.172a2 2 0 00-1.414.586L3 12z"
                        />
                    </svg>
                </button>

                <!-- 0 row -->
                <input
                    type="button"
                    value="C"
                    @click="clear"
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm text-blue-700 font-semibold border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="("
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm text-blue-700 font-semibold border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value=")"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm text-blue-700 font-semibold border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="+"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm text-blue-700 text-5xl border-2 border-gray-300 hover:bg-gray-100"
                />

                <!-- 1st row -->
                <input
                    type="button"
                    value="7"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="8"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="9"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="-"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm text-blue-700 text-5xl border-2 border-gray-300 hover:bg-gray-100"
                />

                <!-- 2nd row -->
                <input
                    type="button"
                    value="4"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="5"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="6"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="×"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm text-blue-700 text-5xl border-2 border-gray-300 hover:bg-gray-100"
                />

                <!-- 3rd row -->
                <input
                    type="button"
                    value="1"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="2"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="3"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="÷"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm text-blue-700 text-5xl border-2 border-gray-300 hover:bg-gray-100"
                />

                <!-- 4th row -->
                <input
                    type="button"
                    value="0"
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm col-span-2 border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="."
                    @mousedown="insertText($event.target.value); "
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm border-2 border-gray-300 hover:bg-gray-100"
                />
                <input
                    type="button"
                    value="="
                    @click="equal"
                    onmousedown="return false"
                    class="cursor-pointer bg-white rounded-sm text-blue-700 text-5xl border-2 border-gray-300 hover:bg-gray-100"
                />
            </div>
        </div>
    </main>
</template>

<script>
export default {
    data() {
        return {
            total: 0,
            text: ""
        };
    },
    methods: {
        insertText(insert) {
            let textarea = this.$refs.output;
            let start = textarea.selectionStart;
            let end = textarea.selectionEnd;

            // insert text
            textarea.value =
                textarea.value.slice(0, start) +
                insert +
                textarea.value.slice(end);

            // change caret position
            textarea.focus;
            let caretPos = start + insert.length;
            textarea.setSelectionRange(caretPos, caretPos);

            // calculate total
            this.total = this.calculate(textarea.value);
        },

        clear() {
            let textarea = this.$refs.output;

            if (textarea.value.length <= 0) return;

            textarea.value = "";
            this.total = 0;
        },

        back() {
            let textarea = this.$refs.output;
            let caretPos = textarea.selectionStart;

            if (textarea.value.length <= 0) return;
            if (caretPos <= 0) return;

            // remove text based on caret position
            textarea.value = this.removeText(textarea.value, caretPos);

            // change caret position
            textarea.focus;
            textarea.setSelectionRange(caretPos - 1, caretPos - 1);

            // calculate total
            this.total = this.calculate(textarea.value);
        },

        equal() {
            let textarea = this.$refs.output;

            textarea.value = this.total;
        },

        calculate(text) {
            return (
                eval(
                    text
                        .replace(/×/g, "*")
                        .replace(/÷/g, "/")
                        .replace(/\^/g, "**")
                        .replace(/%/g, "/100 ")
                ) || ""
            );
        },

        removeText(text, caretPosition) {
            return (
                text.slice(0, caretPosition - 1) +
                text.slice(caretPosition, text.length)
            );
        }
    }
};
</script>