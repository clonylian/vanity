<template>
    <div id="app" class="remodal-bg render">
        <div class="container" id="content">
            <!--Headline-->
            <!-- <headline></headline> -->

            <!--Description-->
            <!-- <div class="row">
                <div class="col-md-12">
                    <description></description>
                </div>
            </div> -->

            <!--Error-->
            <div v-if="error" class="row">
                <div class="col-md-12">
                    <err :error="error"></err>
                </div>
            </div>

            <div class="row">
                <!--User input-->
                <div class="col-md-6">
                    <userInput
                        :running="running"
                        :cores="cores"
                        @start="startGen"
                        @stop="stopGen"
                        @input-change="setInput"
                    ></userInput>
                </div>

                <!--Statistics-->
                <div class="col-md-6">
                    <statistics
                        :prefix="input.prefix"
                        :suffix="input.suffix"
                        :checksum="input.checksum"
                        :status="status"
                        :first-tick="firstTick"
                    ></statistics>
                </div>
            </div>

            <!--Result-->
            <div class="row">
                <div class="col-md-12">
                    <result :address="result.address" :private-key="result.privateKey"></result>
                </div>
            </div>
            <div class="row">
                <!--User input-->
                <div class="col-md-6">
                    <UserInputy
                        :running="runningy"
                        :cores="coresy"
                        @starty="startGeny"
                        @stopy="stopGeny"
                        @input-changey="setInputy"
                    ></UserInputy>
                </div>

                <!--Statistics-->
                <div class="col-md-6">
                    <Statisticsy
                        :prefix="inputy.prefix"
                        :suffix="inputy.suffix"
                        :checksum="inputy.checksum"
                        :status="statusy"
                        :first-tick="firstTicky"
                    ></Statisticsy>
                </div>
            </div>

            <!--Result-->
            <div class="row">
                <div class="col-md-12">
                    <Resulty :address="resulty.address" :private-key="resulty.privateKey"></Resulty>
                </div>
            </div>
            <div class="row">
                <!--User input-->
                <div class="col-md-6">
                    <UserInputt
                        :running="runningt"
                        :cores="corest"
                        @startt="startGent"
                        @stopt="stopGent"
                        @input-changet="setInputt"
                    ></UserInputt>
                </div>

                <!--Statistics-->
                <div class="col-md-6">
                    <Statisticst
                        :prefix="inputt.prefix"
                        :suffix="inputt.suffix"
                        :checksum="inputt.checksum"
                        :status="statust"
                        :first-tick="firstTickt"
                    ></Statisticst>
                </div>
            </div>

            <!--Result-->
            <div class="row">
                <div class="col-md-12">
                    <Resulttwo :address="resultw.address" :private-key="resultw.privateKey"></Resulttwo>
                </div>
            </div>
            <div class="row">
                <!--User input-->
                <div class="col-md-6">
                    <UserInputthr
                        :running="runningthr"
                        :cores="coresthr"
                        @startthr="startGenthr"
                        @stopthr="stopGenthr"
                        @input-changethr="setInputthr"
                    ></UserInputthr>
                </div>

                <!--Statistics-->
                <div class="col-md-6">
                    <Statisticsthr
                        :prefix="inputthr.prefix"
                        :suffix="inputthr.suffix"
                        :checksum="inputthr.checksum"
                        :status="statusthr"
                        :first-tick="firstTickthr"
                    ></Statisticsthr>
                </div>
            </div>

            <!--Result-->
            <div class="row">
                <div class="col-md-12">
                    <Resultthr :address="resultthr.address" :private-key="resultthr.privateKey"></Resultthr>
                </div>
            </div>
            <div class="row">
                <!--User input-->
                <div class="col-md-6">
                    <UserInputf
                        :running="runningf"
                        :cores="coresf"
                        @startf="startGenf"
                        @stopf="stopGenf"
                        @input-changef="setInputf"
                    ></UserInputf>
                </div>

                <!--Statistics-->
                <div class="col-md-6">
                    <Statisticsf
                        :prefix="inputf.prefix"
                        :suffix="inputf.suffix"
                        :checksum="inputf.checksum"
                        :status="statusf"
                        :first-tick="firstTickf"
                    ></Statisticsf>
                </div>
            </div>

            <!--Result-->
            <div class="row">
                <div class="col-md-12">
                    <Resultf :address="resultf.address" :private-key="resultf.privateKey"></Resultf>
                </div>
            </div>
        </div>

        <!--Save modal-->
        <save :address="result.address.toLowerCase()" :private-key="result.privateKey"></save>

        <!--Footer-->
        <foot></foot>

        <!--Github corner-->
        <corner></corner>
    </div>
</template>

<script>
    import Worker from './js/vanity.js';

    // import Headline from './vue/Headline';
    // import Description from './vue/Description';
    import Err from './vue/Error';
    import UserInput from './vue/Input';
    import UserInputy from './vue/Inputy.vue';
    import UserInputt from './vue/Inputt.vue';
    import UserInputthr from './vue/Inputthr.vue';
    import UserInputf from './vue/Inputf.vue';

    import Statistics from './vue/Statistics';
    import Statisticsy from './vue/Statisticsy.vue';
    import Statisticst from './vue/Statisticst.vue';
    import Statisticsthr from './vue/Statisticsthr.vue';
    import Statisticsf from './vue/Statisticsf.vue';

    import Result from './vue/Result';
    import Resulty from './vue/Resulty.vue';
    import Resulttwo from './vue/Resultt.vue';
    import Resultthr from './vue/Resultthr.vue';
    import Resultf from './vue/Resultf.vue';

    import Save from './vue/Save.vue';
    import Corner from './vue/Corner';
    import Foot from './vue/Footer';

    export default {
        components: {
            UserInputy,
            UserInputt,
            UserInputthr,
            UserInputf,
            Err,
            UserInput,
            Statistics,
            Statisticsy,
            Statisticst,
            Statisticsthr,
            Statisticsf,
            Result,
            Resulty,
            Resulttwo,
            Resultthr,
            Resultf,
            Save,
            Corner,
            Foot,
        },
        data: function () {
            return {
                running: false,
                runningy: false,
                runningt: false,
                runningthr: false,
                runningf: false,

                status: 'Waiting',
                statusy: 'Waiting',
                statust: 'Waiting',
                statusthr: 'Waiting',
                statusf: 'Waiting',

                workers: [],
                workersy: [],
                workerst: [],
                workersthr: [],
                workersf: [],

                threads: 4,
                threadsy: 4,
                threadst: 4,
                threadsthr: 4,
                threadsf: 4,

                cores: 0,
                coresy: 0,
                corest: 0,
                coresthr: 0,
                coresf: 0,

                result: { address: '', privateKey: '' },
                resulty: { address: '', privateKey: '' },
                resultw: { address: '', privateKey: '' },
                resultthr: { address: '', privateKey: '' },
                resultf: { address: '', privateKey: '' },

                input: { prefix: '', suffix: '', checksum: true },
                inputy: { prefix: '', suffix: '', checksum: true },
                inputt: { prefix: '', suffix: '', checksum: true },
                inputthr: { prefix: '', suffix: '', checksum: true },
                inputf: { prefix: '', suffix: '', checksum: true },

                firstTick: null,
                firstTicky: null,
                firstTickt: null,
                firstTickthr: null,
                firstTickf: null,

                error: null,
            };
        },
        watch: {
            threads: function () {
                if (!this.running) {
                    this.initWorkers();
                }
            },
            threadsy: function () {
                if (!this.runningy) {
                    this.initWorkersy();
                }
            },
            threadst: function () {
                if (!this.runningt) {
                    this.initWorkerst();
                }
            },
            threadsthr: function () {
                if (!this.runningthr) {
                    this.initWorkersthr();
                }
            },
            threadsf: function () {
                if (!this.runningf) {
                    this.initWorkersf();
                }
            },
        },
        methods: {
            setInput: function (inputType, value) {
                // eslint-disable-next-line default-case
                switch (inputType) {
                    case 'prefix':
                        this.input.prefix = value;
                        break;
                    case 'suffix':
                        this.input.suffix = value;
                        break;
                    case 'checksum':
                        this.input.checksum = value;
                        break;
                    case 'threads':
                        this.threads = value;
                }
            },
            setInputy: function (inputType, value) {
                // eslint-disable-next-line default-case
                switch (inputType) {
                    case 'prefix':
                        this.inputy.prefix = value;
                        break;
                    case 'suffix':
                        this.inputy.suffix = value;
                        break;
                    case 'checksum':
                        this.inputy.checksum = value;
                        break;
                    case 'threads':
                        this.threadsy = value;
                }
            },
            setInputt: function (inputType, value) {
                // eslint-disable-next-line default-case
                switch (inputType) {
                    case 'prefix':
                        this.inputt.prefix = value;
                        break;
                    case 'suffix':
                        this.inputt.suffix = value;
                        break;
                    case 'checksum':
                        this.inputt.checksum = value;
                        break;
                    case 'threads':
                        this.threadst = value;
                }
            },
            setInputthr: function (inputType, value) {
                // eslint-disable-next-line default-case
                switch (inputType) {
                    case 'prefix':
                        this.inputthr.prefix = value;
                        break;
                    case 'suffix':
                        this.inputthr.suffix = value;
                        break;
                    case 'checksum':
                        this.inputthr.checksum = value;
                        break;
                    case 'threads':
                        this.threadsthr = value;
                }
            },
            setInputf: function (inputType, value) {
                // eslint-disable-next-line default-case
                switch (inputType) {
                    case 'prefix':
                        this.inputf.prefix = value;
                        break;
                    case 'suffix':
                        this.inputf.suffix = value;
                        break;
                    case 'checksum':
                        this.inputf.checksum = value;
                        break;
                    case 'threads':
                        this.threadsf = value;
                }
            },
            displayResult: function (result) {
                this.$emit('increment-counter', result.attempts);
                this.result.address = result.address;
                this.result.privateKey = result.privKey;
                this.status = 'Address found';
            },
            displayResulty: function (result) {
                this.$emit('increment-countery', result.attempts);
                this.resulty.address = result.address;
                this.resulty.privateKey = result.privKey;
                this.statusy = 'Address found';
            },
            displayResultt: function (result) {
                this.$emit('increment-countert', result.attempts);
                this.resultw.address = result.address;
                this.resultw.privateKey = result.privKey;
                this.statust = 'Address found';
            },
            displayResultthr: function (result) {
                this.$emit('increment-counterthr', result.attempts);
                this.resultthr.address = result.address;
                this.resultthr.privateKey = result.privKey;
                this.statusthr = 'Address found';
            },
            displayResultf: function (result) {
                this.$emit('increment-counterf', result.attempts);
                this.resultf.address = result.address;
                this.resultf.privateKey = result.privKey;
                this.statusf = 'Address found';
            },
            clearResult: function () {
                this.result.address = '';
                this.result.privateKey = '';
                this.$emit('increment-counter', -1);
            },

            clearResulty: function () {
                this.resulty.address = '';
                this.resulty.privateKey = '';
                this.$emit('increment-countery', -1);
            },

            clearResultt: function () {
                this.resultw.address = '';
                this.resultw.privateKey = '';
                this.$emit('increment-countert', -1);
            },

            clearResultthr: function () {
                this.resultthr.address = '';
                this.resultthr.privateKey = '';
                this.$emit('increment-counterthr', -1);
            },

            clearResultf: function () {
                this.resultf.address = '';
                this.resultf.privateKey = '';
                this.$emit('increment-counterf', -1);
            },

            /**
             * Create missing workers, remove the unwanted ones.
             */
            initWorkers: function () {
                const self = this;
                if (this.workers.length === this.threads) {
                    return;
                }

                // Remove unwanted workers
                if (this.workers.length > this.threads) {
                    for (let w = this.threads; w < this.workers.length; w++) {
                        this.workers[w].terminate();
                    }
                    this.workers = this.workers.slice(0, this.threads);
                    return;
                }

                // Create workers
                for (let w = this.workers.length; w < this.threads; w++) {
                    try {
                        this.workers[w] = new Worker();
                        this.workers[w].onmessage = (event) => self.parseWorkerMessage(event.data);
                    } catch (err) {
                        this.error = err;
                        this.status = 'Error';
                        console.error(this.error);
                        break;
                    }
                }
            },
            initWorkersy: function () {
                const self = this;
                if (this.workersy.length === this.threadsy) {
                    return;
                }

                // Remove unwanted workers
                if (this.workersy.length > this.threadsy) {
                    for (let w = this.threadsy; w < this.workersy.length; w++) {
                        this.workersy[w].terminate();
                    }
                    this.workersy = this.workersy.slice(0, this.threadsy);
                    return;
                }

                // Create workers
                for (let w = this.workersy.length; w < this.threadsy; w++) {
                    try {
                        this.workersy[w] = new Worker();
                        this.workersy[w].onmessage = (event) => self.parseWorkerMessagey(event.data);
                    } catch (err) {
                        this.error = err;
                        this.statusy = 'Error';
                        console.error(this.error);
                        break;
                    }
                }
            },
            initWorkerst: function () {
                const self = this;
                if (this.workerst.length === this.threadst) {
                    return;
                }

                // Remove unwanted workers
                if (this.workerst.length > this.threadst) {
                    for (let w = this.threadst; w < this.workerst.length; w++) {
                        this.workerst[w].terminate();
                    }
                    this.workerst = this.workerst.slice(0, this.threadst);
                    return;
                }

                // Create workers
                for (let w = this.workerst.length; w < this.threadst; w++) {
                    try {
                        this.workerst[w] = new Worker();
                        this.workerst[w].onmessage = (event) => self.parseWorkerMessaget(event.data);
                    } catch (err) {
                        this.error = err;
                        this.statust = 'Error';
                        console.error(this.error);
                        break;
                    }
                }
            },
            initWorkersthr: function () {
                const self = this;
                if (this.workersthr.length === this.threadsthr) {
                    return;
                }

                // Remove unwanted workers
                if (this.workersthr.length > this.threadsthr) {
                    for (let w = this.threadsthr; w < this.workersthr.length; w++) {
                        this.workersthr[w].terminate();
                    }
                    this.workersthr = this.workersthr.slice(0, this.threadsthr);
                    return;
                }

                // Create workers
                for (let w = this.workersthr.length; w < this.threadsthr; w++) {
                    try {
                        this.workersthr[w] = new Worker();
                        this.workersthr[w].onmessage = (event) => self.parseWorkerMessagethr(event.data);
                    } catch (err) {
                        this.error = err;
                        this.statusthr = 'Error';
                        console.error(this.error);
                        break;
                    }
                }
            },
            initWorkersf: function () {
                const self = this;
                if (this.workersf.length === this.threadsf) {
                    return;
                }

                // Remove unwanted workers
                if (this.workersf.length > this.threadsf) {
                    for (let w = this.threadsf; w < this.workersf.length; w++) {
                        this.workersf[w].terminate();
                    }
                    this.workersf = this.workersf.slice(0, this.threadsf);
                    return;
                }

                // Create workers
                for (let w = this.workersf.length; w < this.threadsf; w++) {
                    try {
                        this.workersf[w] = new Worker();
                        this.workersf[w].onmessage = (event) => self.parseWorkerMessagef(event.data);
                    } catch (err) {
                        this.error = err;
                        this.statusf = 'Error';
                        console.error(this.error);
                        break;
                    }
                }
            },
            parseWorkerMessage: function (wallet) {
                if (wallet.error) {
                    this.stopGen();
                    this.error = wallet.error;
                    this.status = 'Error';
                    console.error(this.error);
                    return;
                }

                if (wallet.address) {
                    this.stopGen();
                    return this.displayResult(wallet);
                }
                this.$emit('increment-counter', wallet.attempts);
            },
            parseWorkerMessagey: function (wallet) {
                if (wallet.error) {
                    this.stopGeny();
                    this.error = wallet.error;
                    this.statusy = 'Error';
                    console.error(this.error);
                    return;
                }

                if (wallet.address) {
                    this.stopGeny();
                    return this.displayResulty(wallet);
                }
                this.$emit('increment-countery', wallet.attempts);
            },
            parseWorkerMessaget: function (wallet) {
                if (wallet.error) {
                    this.stopGent();
                    this.error = wallet.error;
                    this.statust = 'Error';
                    console.error(this.error);
                    return;
                }

                if (wallet.address) {
                    this.stopGent();
                    return this.displayResultt(wallet);
                }
                this.$emit('increment-countert', wallet.attempts);
            },
            parseWorkerMessagethr: function (wallet) {
                if (wallet.error) {
                    this.stopGenthr();
                    this.error = wallet.error;
                    this.statusthr = 'Error';
                    console.error(this.error);
                    return;
                }

                if (wallet.address) {
                    this.stopGenthr();
                    return this.displayResultthr(wallet);
                }
                this.$emit('increment-counterthr', wallet.attempts);
            },
            parseWorkerMessagef: function (wallet) {
                if (wallet.error) {
                    this.stopGenf();
                    this.error = wallet.error;
                    this.statusf = 'Error';
                    console.error(this.error);
                    return;
                }

                if (wallet.address) {
                    this.stopGenf();
                    return this.displayResultf(wallet);
                }
                this.$emit('increment-counterf', wallet.attempts);
            },

            startGen: function () {
                if (!window.Worker) {
                    this.error = 'workers_unsupported';
                    return;
                }

                this.clearResult();
                this.running = true;

                for (let w = 0; w < this.workers.length; w++) {
                    this.workers[w].postMessage(this.input);
                }

                this.status = 'Running';
                this.firstTick = performance.now();
            },
            startGeny: function () {
                if (!window.Worker) {
                    this.error = 'workers_unsupported';
                    return;
                }

                this.clearResulty();
                this.runningy = true;

                for (let w = 0; w < this.workersy.length; w++) {
                    this.workersy[w].postMessage(this.inputy);
                }

                this.statusy = 'Running';
                this.firstTicky = performance.now();
            },
            startGent: function () {
                if (!window.Worker) {
                    this.error = 'workers_unsupported';
                    return;
                }

                this.clearResultt();
                this.runningt = true;

                for (let w = 0; w < this.workerst.length; w++) {
                    this.workerst[w].postMessage(this.inputt);
                }

                this.statust = 'Running';
                this.firstTickt = performance.now();
            },
            startGenthr: function () {
                if (!window.Worker) {
                    this.error = 'workers_unsupported';
                    return;
                }

                this.clearResultthr();
                this.runningthr = true;

                for (let w = 0; w < this.workersthr.length; w++) {
                    this.workersthr[w].postMessage(this.inputthr);
                }

                this.statusthr = 'Running';
                this.firstTickthr = performance.now();
            },
            startGenf: function () {
                if (!window.Worker) {
                    this.error = 'workers_unsupported';
                    return;
                }

                this.clearResultf();
                this.runningf = true;

                for (let w = 0; w < this.workersf.length; w++) {
                    this.workersf[w].postMessage(this.inputf);
                }

                this.statusy = 'Running';
                this.firstTicky = performance.now();
            },
            stopGen: function () {
                this.running = false;
                this.status = 'Stopped';
                for (let i = 0; i < this.workers.length; i++) {
                    this.workers[i].terminate();
                }
                this.workers = [];
                this.initWorkers();
            },
            stopGeny: function () {
                this.runningy = false;
                this.statusy = 'Stopped';
                for (let i = 0; i < this.workersy.length; i++) {
                    this.workersy[i].terminate();
                }
                this.workersy = [];
                this.initWorkersy();
            },
            stopGent: function () {
                this.runningt = false;
                this.statust = 'Stopped';
                for (let i = 0; i < this.workerst.length; i++) {
                    this.workerst[i].terminate();
                }
                this.workerst = [];
                this.initWorkerst();
            },
            stopGenthr: function () {
                this.runningthr = false;
                this.statusthr = 'Stopped';
                for (let i = 0; i < this.workersthr.length; i++) {
                    this.workersthr[i].terminate();
                }
                this.workersthr = [];
                this.initWorkersthr();
            },
            stopGenf: function () {
                this.runningf = false;
                this.statusf = 'Stopped';
                for (let i = 0; i < this.workersf.length; i++) {
                    this.workersf[i].terminate();
                }
                this.workersf = [];
                this.initWorkersf();
            },
            countCores: function () {
                // Estimate number of cores on machine
                let cores = 0;
                try {
                    cores = parseInt(navigator.hardwareConcurrency, 10);
                } catch (err) {
                    console.error(err);
                }

                if (cores) {
                    this.cores = cores;
                    this.threads = this.cores;
                }
            },
            checkLocation() {
                try {
                    this.error = window.self !== window.top ? 'insecure_location' : this.error;
                } catch (e) {
                    this.error = 'insecure_location';
                }
                const hostname = window.location.hostname;
                if (hostname && ['localhost', '127.0.0.1', 'vanity-eth.tk'].indexOf(hostname) === -1) {
                    this.error = 'insecure_location';
                }
            },
            benchmark(max) {
                max = max || 10000;
                const step = 500;
                const worker = new Worker();
                let attempts = 0;
                const times = [];
                const durations = [];
                const timeTaken = (a, d) => Math.round((1000 * a) / d);
                worker.onmessage = () => {
                    times.push(performance.now());
                    if (times.length === 1) {
                        return;
                    }
                    durations.push(times[times.length - 1] - times[times.length - 2]);
                    attempts += step;
                    console.info(
                        attempts + '/' + max + '...' + timeTaken(step, durations[durations.length - 1]) + ' addr/s'
                    );
                    if (attempts >= max) {
                        console.info(
                            '\nSpeed range: ' +
                                timeTaken(step, Math.max(...durations)) +
                                ' - ' +
                                timeTaken(step, Math.min(...durations)) +
                                ' addr/s'
                        );
                        console.info('Average: ' + timeTaken(attempts, times[times.length - 1] - times[0]) + ' addr/s');
                        worker.terminate();
                    }
                };
                const input = { checksum: true, prefix: 'f'.repeat(5), suffix: '' };
                console.info('Starting benchmark with 1 core...');
                worker.postMessage(input);
            },
        },

        created: function () {
            this.checkLocation();
            this.countCores();
            this.initWorkers();
            this.initWorkersy();
            this.initWorkerst();
            this.initWorkersthr();
            this.initWorkersf();

            window['benchmark'] = this.benchmark;
        },
    };
</script>

<style lang="sass">
    // Bootstrap - Required
    @import "~bootstrap/scss/functions"
    @import "~bootstrap/scss/variables"
    @import "~bootstrap/scss/mixins"

    // Bootstrap - Optional
    @import "~bootstrap/scss/reboot"
    @import "~bootstrap/scss/grid"

    @import "css/variables"
    @import "css/fonts"

    body
        padding: 0
        font-family: 'Lato', sans-serif
        background: $bg-fallback
        background: linear-gradient(140deg, $bg-2 0%, $bg-1 100%)
        background-attachment: fixed
        font-size: 16px

    h1, h2, h3, h4, h5, h6, p, label
        margin: 0
        font-weight: normal

    a, a:visited, a:hover
        color: $text-alt
        text-decoration: underline

    a:hover
        color: $text

    .panel
        padding: 1.5em 3em
        background-color: $panel-background
        margin-top: 2em
        color: $text
        font-weight: 400
        box-shadow: $shadow
        transition: box-shadow 0.2s ease-in-out
        &:hover
            box-shadow: $shadow-big

    #content
        margin-top: 8em
        margin-bottom: 6em

    .text-input-large
        width: 100%
        color: $text
        background: $panel-background-alt
        outline: none
        font-size: 1.3em
        padding: 0.5em
        border: none
        margin-bottom: 10px
        -webkit-appearance: none
        &::placeholder
            color: $placeholder

    .button-large
        border: none
        outline: none
        color: $text-opposite
        padding: 8px
        font-size: 19px
        font-weight: 500
        margin: 1.3em 0 0 0
        cursor: pointer
        -webkit-appearance: none
        background: $primary
        width: 100%
        &:hover
            background: $secondary
        &:disabled
            background: $disabled
            cursor: auto

    /*-- Pre-render-specific --

    #app.render .hide-render
        display: none

    #app.prerender .hide-prerender
        display: none

    /*-- Responsive design --

    @media screen and (max-width: 1024px)
        #content
            margin-top: 7em
            margin-bottom: 5em

    @media screen and (max-width: 640px)
        #content
            margin-top: 5em
            margin-bottom: 4em

    @media screen and (max-width: 480px)
        .panel
            padding: 1em
</style>
