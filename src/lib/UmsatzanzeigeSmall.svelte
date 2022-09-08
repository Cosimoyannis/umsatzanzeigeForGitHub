<svelte:options tag="my-umsatzanzeigesmall" />

<script>
    import { getContext, onMount } from "svelte";
    import Chart from "chart.js/auto/auto.js";

    // saldo calculation MONTH

    let umsaetzeJan = [
        4484, 683, 2553, 2490, 4047, 4006, 3612, 577, 1873, 9846, 9766, 9420,
        3486, 9894, 5606, 2009, 657, 5125, 8328, 3862, 3786, 387, 5092, 979,
        1879, 271, 1207, 4099, 3878, 8856, 8437,
    ];

    let umsaetzeFeb = [
        9385, 6378, 6473, 1116, 8372, 6053, 6881, 6662, 9214, 5377, 357, 8180,
        9921, 9073, 4665, 2964, 4175, 535, 7445, 6319, 6644, 3160, 5604, 1838,
        1465, 6034, 9698, 7970, 8983,
    ];

    let umsaetzeMär = [
        5030, 5740, 7915, 5661, 1878, 5242, 8754, 332, 6648, 8075, 3955, 4516,
        3213, 3317, 2549, 2243, 5003, 5885, 6462, 9095, 8529, 5421, 6324, 4253,
        2590, 2974, 6938, 5145, 7530, 1779, 9446,
    ];

    let umsaetzeApr = [
        5156, 1069, 2780, 4392, 6631, 1510, 8714, 8728, 1454, 7085, 6385, 8739,
        5934, 2468, 68, 6120, 352, 3475, 5272, 1596, 8094, 1560, 8916, 1847,
        7765, 6887, 4562, 1718, 4412, 8437, 1607,
    ];

    let umsaetzeMai = [
        3559, 8572, 3665, 1914, 4657, 8344, 2617, 6090, 2904, 611, 7257, 4764,
        4064, 4335, 8109, 3439, 6926, 7550, 596, 6703, 5510, 8692, 4765, 3440,
        7767, 6101, 8255, 4950, 2034, 8283, 6361,
    ];

    let umsaetzeJun = [
        4320, 1178, 7252, 9606, 2548, 6180, 4105, 3154, 5963, 1990, 6538, 7810,
        3059, 923, 5228, 1417, 6670, 6406, 2153, 3388, 5089, 3991, 9931, 2022,
        3893, 6064, 4983, 258, 7945, 5406, 3814,
    ];

    let umsaetzeJul = [
        1967, 8047, 5011, 2041, 3743, 5546, 2709, 9242, 3528, 1482, 493, 654,
        3242, 5712, 4831, 469, 2468, 476, 2244, 1859, 6017, 611, 1125, 8798,
        5005, 9805, 3514, 8722, 2276, 9286, 9102,
    ];

    let umsaetzeAug = [
        6532, 63, 9893, 9220, 1686, 5283, 1332, 5581, 7644, 1956, 9639, 4800,
        2392, 7828, 8856, 4232, 2684, 5709, 3764, 2305, 3520, 448, 1113, 6999,
        865, 587, 7667, 4860, 3215, 3278, 174,
    ];

    let umsaetzeSep = [
        6065, 4835, 1894, 887, 5957, 7583, 8268, 7004, 3091, 8164, 7953, 4450,
        1981, 3826, 1356, 9523, 5978, 4640, 8571, 9682, 6326, 3873, 1823, 8403,
        1120, 9881, 6228, 7577, 1547, 1379, 2460,
    ];

    let umsaetzeOkt = [
        5262, 785, 4037, 9069, 7005, 8484, 4769, 4221, 9614, 4055, 7077, 5116,
        7889, 8779, 9649, 1743, 7561, 2919, 3528, 8329, 7624, 8328, 2173, 2253,
        5185, 2553, 3136, 6595, 817, 9500, 7282,
    ];

    let umsaetzeNov = [
        6909, 2420, 5779, 6475, 5117, 7072, 1105, 6402, 2709, 198, 2226, 22,
        2840, 414, 8253, 7388, 998, 9081, 2698, 4029, 5161, 8946, 9572, 9975,
        9906, 5765, 7074, 5842, 846, 95, 7958,
    ];

    let umsaetzeDez = [
        4237, 1915, 1388, 6869, 4304, 5565, 9449, 4339, 1652, 8683, 5266, 6916,
        2101, 4659, 4255, 2219, 4216, 1498, 982, 7676, 4082, 8163, 7906, 1797,
        5909, 7241, 9279, 6554, 2854, 6780, 8437,
    ];

    // saldo calculation YEAR

    let saldo2017 = 0;

    //SALDO 2018
    let saldoJan2018 = saldo2017 + 2000;

    let saldoFeb2018 = saldoJan2018 - 4000;

    let saldoMär2018 = saldoFeb2018 + 1000;

    let saldoApr2018 = saldoMär2018 + 4000;

    let saldoMai2018 = saldoApr2018 + 2000;

    let saldoJun2018 = saldoMai2018 + 5000;

    let saldoJul2018 = saldoJun2018 - 1000;

    let saldoAug2018 = saldoJul2018 - 2000;

    let saldoSep2018 = saldoAug2018 + 8000;

    let saldoOkt2018 = saldoSep2018 + 1000;

    let saldoNov2018 = saldoOkt2018 + 2000;

    let saldoDez2018 = saldoNov2018 - 9000;

    //SALDO 2019
    let saldoJan2019 = saldoDez2018 + 2000;

    let saldoFeb2019 = saldoJan2019 + 4000;

    let saldoMär2019 = saldoFeb2019 + 1000;

    let saldoApr2019 = saldoMär2019 + 4000;

    let saldoMai2019 = saldoApr2019 - 2000;

    let saldoJun2019 = saldoMai2019 + 5000;

    let saldoJul2019 = saldoJun2019 + 1000;

    let saldoAug2019 = saldoJul2019 + 2000;

    let saldoSep2019 = saldoAug2019 + 8000;

    let saldoOkt2019 = saldoSep2019 + 1000;

    let saldoNov2019 = saldoOkt2019 - 2000;

    let saldoDez2019 = saldoNov2019 - 9000;

    //SALDO 2020
    let saldoJan2020 = saldoDez2019 + 1000;

    let saldoFeb2020 = saldoJan2020 - 1000;

    let saldoMär2020 = saldoFeb2020 + 8000;

    let saldoApr2020 = saldoMär2020 - 2000;

    let saldoMai2020 = saldoApr2020 + 7000;

    let saldoJun2020 = saldoMai2020 - 4000;

    let saldoJul2020 = saldoJun2020 - 9000;

    let saldoAug2020 = saldoJul2020 + 10000;

    let saldoSep2020 = saldoAug2020 + 2000;

    let saldoOkt2020 = saldoSep2020 - 4000;

    let saldoNov2020 = saldoOkt2020 - 7000;

    let saldoDez2020 = saldoNov2020 - 7000;

    //SALDO 2021
    let saldoJan2021 = saldoDez2020 + 2000;

    let saldoFeb2021 = saldoJan2021 - 1000;

    let saldoMär2021 = saldoFeb2021 + 8000;

    let saldoApr2021 = saldoMär2021 - 2000;

    let saldoMai2021 = saldoApr2021 + 7000;

    let saldoJun2021 = saldoMai2021 + 3000;

    let saldoJul2021 = saldoJun2021 + 9000;

    let saldoAug2021 = saldoJul2021 - 10000;

    let saldoSep2021 = saldoAug2021 + 1000;

    let saldoOkt2021 = saldoSep2021 - 2000;

    let saldoNov2021 = saldoOkt2021 + 1000;

    let saldoDez2021 = saldoNov2021 - 1000;

    //SALDO 2022
    let saldoJan2022 = saldoDez2021 + 1000;

    let saldoFeb2022 = saldoJan2022 + 2000;

    let saldoMär2022 = saldoFeb2022 + 4000;

    let saldoApr2022 = saldoMär2022 - 2000;

    let saldoMai2022 = saldoApr2022 + 1000;

    let saldoJun2022 = saldoMai2022 - 2000;

    let saldoJul2022 = saldoJun2022 + 4000;

    let saldoAug2022 = saldoJul2022 + 2000;

    let saldoSep2022 = saldoAug2022 + 1000;

    let saldoOkt2022 = saldoSep2022 + 4000;

    let saldoNov2022 = saldoOkt2022 - 9000;

    let saldoDez2022 = saldoNov2022 - 1000;

    // get Date Methoden

    var utc = new Date();

    let formatted_date =
        utc.getDate() + "/" + (utc.getMonth() + 1) + "/" + utc.getFullYear();

    let choosenDate = new Date(2022);

    function getAllDaysInMonth(year, month) {
        const date = new Date(year, month, 1);

        const dates = [];

        while (date.getMonth() === month) {
            dates.push(new Date(date));
            date.setDate(date.getDate() + 1);
        }

        return dates;
    }

    function getDaysInMonth(month, year) {
        var date = new Date(year, month, 1);
        var days = [];
        while (date.getMonth() === month) {
            days.push(new Date(date.toLocaleDateString("en-US")));
            date.setDate(date.getDate() + 1);
        }
        return days;
    }

    let dateJanuar2018 = new Date("2018-01-01");
    let dateFebruar2018 = new Date("2018-02-01");
    let dateMärz2018 = new Date("2018-03-01");
    let dateApril2018 = new Date("2018-04-01");
    let dateMai2018 = new Date("2018-05-01");
    let dateJuni2018 = new Date("2018-06-01");
    let dateJuli2018 = new Date("2018-07-01");
    let dateAugust2018 = new Date("2018-08-01");
    let dateSeptember2018 = new Date("2018-09-01");
    let dateOktober2018 = new Date("2018-10-01");
    let dateNovember2018 = new Date("2018-11-01");
    let dateDezember2018 = new Date("2018-12-01");

    let dateJanuar2019 = new Date("2019-01-01");
    let dateFebruar2019 = new Date("2019-02-01");
    let dateMärz2019 = new Date("2019-03-01");
    let dateApril2019 = new Date("2019-04-01");
    let dateMai2019 = new Date("2019-05-01");
    let dateJuni2019 = new Date("2019-06-01");
    let dateJuli2019 = new Date("2019-07-01");
    let dateAugust2019 = new Date("2019-08-01");
    let dateSeptember2019 = new Date("2019-09-01");
    let dateOktober2019 = new Date("2019-10-01");
    let dateNovember2019 = new Date("2019-11-01");
    let dateDezember2019 = new Date("2019-12-01");

    let dateJanuar2020 = new Date("2020-01-01");
    let dateFebruar2020 = new Date("2020-02-01");
    let dateMärz2020 = new Date("2020-03-01");
    let dateApril2020 = new Date("2020-04-01");
    let dateMai2020 = new Date("2020-05-01");
    let dateJuni2020 = new Date("2020-06-01");
    let dateJuli2020 = new Date("2020-07-01");
    let dateAugust2020 = new Date("2020-08-01");
    let dateSeptember2020 = new Date("2020-09-01");
    let dateOktober2020 = new Date("2020-10-01");
    let dateNovember2020 = new Date("2020-11-01");
    let dateDezember2020 = new Date("2020-12-01");

    let dateJanuar2021 = new Date("2021-01-01");
    let dateFebruar2021 = new Date("2021-02-01");
    let dateMärz2021 = new Date("2021-03-01");
    let dateApril2021 = new Date("2021-04-01");
    let dateMai2021 = new Date("2021-05-01");
    let dateJuni2021 = new Date("2021-06-01");
    let dateJuli2021 = new Date("2021-07-01");
    let dateAugust2021 = new Date("2021-08-01");
    let dateSeptember2021 = new Date("2021-09-01");
    let dateOktober2021 = new Date("2021-10-01");
    let dateNovember2021 = new Date("2021-11-01");
    let dateDezember2021 = new Date("2021-12-01");

    let dateJanuar2022 = new Date("2022-01-01");
    let dateFebruar2022 = new Date("2022-02-01");
    let dateMärz2022 = new Date("2022-03-01");
    let dateApril2022 = new Date("2022-04-01");
    let dateMai2022 = new Date("2022-05-01");
    let dateJuni2022 = new Date("2022-06-01");
    let dateJuli2022 = new Date("2022-07-01");
    let dateAugust2022 = new Date("2022-08-01");
    let dateSeptember2022 = new Date("2022-09-01");
    let dateOktober2022 = new Date("2022-10-01");
    let dateNovember2022 = new Date("2022-11-01");
    let dateDezember2022 = new Date("2022-12-01");

    // Array mit Daten

    let YearDatasets = [
        {
            year: 2018,
            umsätze: [
                saldoJan2018,
                saldoFeb2018,
                saldoMär2018,
                saldoApr2018,
                saldoMai2018,
                saldoJun2018,
                saldoJul2018,
                saldoAug2018,
                saldoSep2018,
                saldoOkt2018,
                saldoNov2018,
                saldoDez2018,
            ],
            umsätzeMonths: {
                Januar: umsaetzeJan,
                Februar: umsaetzeFeb,
                März: umsaetzeMär,
                April: umsaetzeApr,
                Mai: umsaetzeMai,
                Juni: umsaetzeJun,
                Juli: umsaetzeJul,
                August: umsaetzeAug,
                September: umsaetzeSep,
                Oktober: umsaetzeOkt,
                November: umsaetzeNov,
                Dezember: umsaetzeDez,
            },
            daysInMonth: {
                Januar: getAllDaysInMonth(
                    dateJanuar2018.getFullYear(),
                    dateJanuar2018.getMonth()
                ),
                Februar: getAllDaysInMonth(
                    dateFebruar2018.getFullYear(),
                    dateFebruar2018.getMonth()
                ),
                März: getAllDaysInMonth(
                    dateMärz2018.getFullYear(),
                    dateMärz2018.getMonth()
                ),
                April: getAllDaysInMonth(
                    dateApril2018.getFullYear(),
                    dateApril2018.getMonth()
                ),
                Mai: getAllDaysInMonth(
                    dateMai2018.getFullYear(),
                    dateMai2018.getMonth()
                ),
                Juni: getAllDaysInMonth(
                    dateJuni2018.getFullYear(),
                    dateJuni2018.getMonth()
                ),
                Juli: getAllDaysInMonth(
                    dateJuli2018.getFullYear(),
                    dateJuli2018.getMonth()
                ),
                August: getAllDaysInMonth(
                    dateAugust2018.getFullYear(),
                    dateAugust2018.getMonth()
                ),
                September: getAllDaysInMonth(
                    dateSeptember2018.getFullYear(),
                    dateSeptember2018.getMonth()
                ),
                Oktober: getAllDaysInMonth(
                    dateOktober2018.getFullYear(),
                    dateOktober2018.getMonth()
                ),
                November: getAllDaysInMonth(
                    dateNovember2018.getFullYear(),
                    dateNovember2018.getMonth()
                ),
                Dezember: getAllDaysInMonth(
                    dateDezember2018.getFullYear(),
                    dateDezember2018.getMonth()
                ),
            },
        },

        {
            year: 2019,
            umsätze: [
                saldoJan2019,
                saldoFeb2019,
                saldoMär2019,
                saldoApr2019,
                saldoMai2019,
                saldoJun2019,
                saldoJul2019,
                saldoAug2019,
                saldoSep2019,
                saldoOkt2019,
                saldoNov2019,
                saldoDez2019,
            ],
            umsätzeMonths: {
                Januar: umsaetzeJan,
                Februar: umsaetzeFeb,
                März: umsaetzeMär,
                April: umsaetzeApr,
                Mai: umsaetzeMai,
                Juni: umsaetzeJun,
                Juli: umsaetzeJul,
                August: umsaetzeAug,
                September: umsaetzeSep,
                Oktober: umsaetzeOkt,
                November: umsaetzeNov,
                Dezember: umsaetzeDez,
            },
            daysInMonth: {
                Januar: getAllDaysInMonth(
                    dateJanuar2019.getFullYear(),
                    dateJanuar2019.getMonth()
                ),
                Februar: getAllDaysInMonth(
                    dateFebruar2019.getFullYear(),
                    dateFebruar2019.getMonth()
                ),
                März: getAllDaysInMonth(
                    dateMärz2019.getFullYear(),
                    dateMärz2019.getMonth()
                ),
                April: getAllDaysInMonth(
                    dateApril2019.getFullYear(),
                    dateApril2019.getMonth()
                ),
                Mai: getAllDaysInMonth(
                    dateMai2019.getFullYear(),
                    dateMai2019.getMonth()
                ),
                Juni: getAllDaysInMonth(
                    dateJuni2019.getFullYear(),
                    dateJuni2019.getMonth()
                ),
                Juli: getAllDaysInMonth(
                    dateJuli2019.getFullYear(),
                    dateJuli2019.getMonth()
                ),
                August: getAllDaysInMonth(
                    dateAugust2019.getFullYear(),
                    dateAugust2019.getMonth()
                ),
                September: getAllDaysInMonth(
                    dateSeptember2019.getFullYear(),
                    dateSeptember2019.getMonth()
                ),
                Oktober: getAllDaysInMonth(
                    dateOktober2019.getFullYear(),
                    dateOktober2019.getMonth()
                ),
                November: getAllDaysInMonth(
                    dateNovember2019.getFullYear(),
                    dateNovember2019.getMonth()
                ),
                Dezember: getAllDaysInMonth(
                    dateDezember2019.getFullYear(),
                    dateDezember2019.getMonth()
                ),
            },
        },

        {
            year: 2020,
            umsätze: [
                saldoJan2020,
                saldoFeb2020,
                saldoMär2020,
                saldoApr2020,
                saldoMai2020,
                saldoJun2020,
                saldoJul2020,
                saldoAug2020,
                saldoSep2020,
                saldoOkt2020,
                saldoNov2020,
                saldoDez2020,
            ],
            umsätzeMonths: {
                Januar: umsaetzeJan,
                Februar: umsaetzeFeb,
                März: umsaetzeMär,
                April: umsaetzeApr,
                Mai: umsaetzeMai,
                Juni: umsaetzeJun,
                Juli: umsaetzeJul,
                August: umsaetzeAug,
                September: umsaetzeSep,
                Oktober: umsaetzeOkt,
                November: umsaetzeNov,
                Dezember: umsaetzeDez,
            },
            daysInMonth: {
                Januar: getAllDaysInMonth(
                    dateJanuar2020.getFullYear(),
                    dateJanuar2020.getMonth()
                ),
                Februar: getAllDaysInMonth(
                    dateFebruar2020.getFullYear(),
                    dateFebruar2020.getMonth()
                ),
                März: getAllDaysInMonth(
                    dateMärz2020.getFullYear(),
                    dateMärz2020.getMonth()
                ),
                April: getAllDaysInMonth(
                    dateApril2020.getFullYear(),
                    dateApril2020.getMonth()
                ),
                Mai: getAllDaysInMonth(
                    dateMai2020.getFullYear(),
                    dateMai2020.getMonth()
                ),
                Juni: getAllDaysInMonth(
                    dateJuni2020.getFullYear(),
                    dateJuni2020.getMonth()
                ),
                Juli: getAllDaysInMonth(
                    dateJuli2020.getFullYear(),
                    dateJuli2020.getMonth()
                ),
                August: getAllDaysInMonth(
                    dateAugust2020.getFullYear(),
                    dateAugust2020.getMonth()
                ),
                September: getAllDaysInMonth(
                    dateSeptember2020.getFullYear(),
                    dateSeptember2020.getMonth()
                ),
                Oktober: getAllDaysInMonth(
                    dateOktober2020.getFullYear(),
                    dateOktober2020.getMonth()
                ),
                November: getAllDaysInMonth(
                    dateNovember2020.getFullYear(),
                    dateNovember2020.getMonth()
                ),
                Dezember: getAllDaysInMonth(
                    dateDezember2020.getFullYear(),
                    dateDezember2020.getMonth()
                ),
            },
        },

        {
            year: 2021,
            umsätze: [
                saldoJan2021,
                saldoFeb2021,
                saldoMär2021,
                saldoApr2021,
                saldoMai2021,
                saldoJun2021,
                saldoJul2021,
                saldoAug2021,
                saldoSep2021,
                saldoOkt2021,
                saldoNov2021,
                saldoDez2021,
            ],
            umsätzeMonths: {
                Januar: umsaetzeJan,
                Februar: umsaetzeFeb,
                März: umsaetzeMär,
                April: umsaetzeApr,
                Mai: umsaetzeMai,
                Juni: umsaetzeJun,
                Juli: umsaetzeJul,
                August: umsaetzeAug,
                September: umsaetzeSep,
                Oktober: umsaetzeOkt,
                November: umsaetzeNov,
                Dezember: umsaetzeDez,
            },
            daysInMonth: {
                Januar: getAllDaysInMonth(
                    dateJanuar2021.getFullYear(),
                    dateJanuar2021.getMonth()
                ),
                Februar: getAllDaysInMonth(
                    dateFebruar2021.getFullYear(),
                    dateFebruar2021.getMonth()
                ),
                März: getAllDaysInMonth(
                    dateMärz2021.getFullYear(),
                    dateMärz2021.getMonth()
                ),
                April: getAllDaysInMonth(
                    dateApril2021.getFullYear(),
                    dateApril2021.getMonth()
                ),
                Mai: getAllDaysInMonth(
                    dateMai2021.getFullYear(),
                    dateMai2021.getMonth()
                ),
                Juni: getAllDaysInMonth(
                    dateJuni2021.getFullYear(),
                    dateJuni2021.getMonth()
                ),
                Juli: getAllDaysInMonth(
                    dateJuli2021.getFullYear(),
                    dateJuli2021.getMonth()
                ),
                August: getAllDaysInMonth(
                    dateAugust2021.getFullYear(),
                    dateAugust2021.getMonth()
                ),
                September: getAllDaysInMonth(
                    dateSeptember2021.getFullYear(),
                    dateSeptember2021.getMonth()
                ),
                Oktober: getAllDaysInMonth(
                    dateOktober2021.getFullYear(),
                    dateOktober2021.getMonth()
                ),
                November: getAllDaysInMonth(
                    dateNovember2021.getFullYear(),
                    dateNovember2021.getMonth()
                ),
                Dezember: getAllDaysInMonth(
                    dateDezember2021.getFullYear(),
                    dateDezember2021.getMonth()
                ),
            },
        },

        {
            year: 2022,
            umsätze: [
                saldoJan2022,
                saldoFeb2022,
                saldoMär2022,
                saldoApr2022,
                saldoMai2022,
                saldoJun2022,
                saldoJul2022,
            ],
            umsätzeMonths: {
                Januar: umsaetzeJan,
                Februar: umsaetzeFeb,
                März: umsaetzeMär,
                April: umsaetzeApr,
                Mai: umsaetzeMai,
                Juni: umsaetzeJun,
                Juli: umsaetzeJul,
                August: umsaetzeAug,
                September: umsaetzeSep,
                Oktober: umsaetzeOkt,
                November: umsaetzeNov,
                Dezember: umsaetzeDez,
            },
            daysInMonth: {
                Januar: getAllDaysInMonth(
                    dateJanuar2022.getFullYear(),
                    dateJanuar2022.getMonth()
                ),
                Februar: getAllDaysInMonth(
                    dateFebruar2022.getFullYear(),
                    dateFebruar2022.getMonth()
                ),
                März: getAllDaysInMonth(
                    dateMärz2022.getFullYear(),
                    dateMärz2022.getMonth()
                ),
                April: getAllDaysInMonth(
                    dateApril2022.getFullYear(),
                    dateApril2022.getMonth()
                ),
                Mai: getAllDaysInMonth(
                    dateMai2022.getFullYear(),
                    dateMai2022.getMonth()
                ),
                Juni: getAllDaysInMonth(
                    dateJuni2022.getFullYear(),
                    dateJuni2022.getMonth()
                ),
                Juli: getAllDaysInMonth(
                    dateJuli2022.getFullYear(),
                    dateJuli2022.getMonth()
                ),
                August: getAllDaysInMonth(
                    dateAugust2022.getFullYear(),
                    dateAugust2022.getMonth()
                ),
                September: getAllDaysInMonth(
                    dateSeptember2022.getFullYear(),
                    dateSeptember2022.getMonth()
                ),
                Oktober: getAllDaysInMonth(
                    dateOktober2022.getFullYear(),
                    dateOktober2022.getMonth()
                ),
                November: getAllDaysInMonth(
                    dateNovember2022.getFullYear(),
                    dateNovember2022.getMonth()
                ),
                Dezember: getAllDaysInMonth(
                    dateDezember2022.getFullYear(),
                    dateDezember2022.getMonth()
                ),
            },
        },
    ];

    // const btnTage = document.getElementById('btnTage');
    let btnTage = null;

    // const btnMonate = document.getElementById('btnMonate');
    let btnMonate = null;

    // const btnBar = document.getElementById('btnBar');
    let btnBar = null;

    // const btnLine = document.getElementById('btnLine');
    let btnLine = null;

    // document.getElementById('myChart')
    let canvas = null;

    // document.getElementById("listOne")
    let listOne = null;

    // document.getElementById("listTwo")
    let listTwo = null;

    // document.getElementById("listMonthOne")
    let listMonthOne = null;

    // document.getElementById("listMonthTwo")
    let listMonthTwo = null;

    // var input = document.getElementById('flexSwitchCheckDefault');
    let input = null;

    let myChart = null;

    let ctx = null;

    let gradient = null;

    let gradientTwo = null;

    let gradientBar = null;

    let gradientTwoBar = null;

    // chart Label data

    const labelYear = [
        "Jan",
        "Feb",
        "Mär",
        "Apr",
        "Mai",
        "Jun",
        "Jul",
        "Aug",
        "Sep",
        "Okt",
        "Nov",
        "Dez",
    ];

    // Chart Data
    let data = {
        labels: labelYear, //labelYear
        datasets: [
            {
                label: new Date().getFullYear(),
                fill: true,
                lineTension: 0.3,
                backgroundColor: null,
                borderColor: "rgb(197, 0, 51)",
                borderCapStyle: "butt",
                borderDash: [],
                borderDashOffset: 0.0,
                borderJoinStyle: "round",
                pointHitRadius: 100,
                pointBackgroundColor: "black",
                pointBorderColor: "black",
                pointHoverBorderWidth: 8,
                data: YearDatasets[4].umsätze,
            },
            {
                label: "",
                fill: true,
                lineTension: 0.5,
                backgroundColor: "rgba(130, 130, 130, .6)",
                borderColor: "rgb(130, 130, 130)",
                borderCapStyle: "butt",
                borderDash: [],
                borderDashOffset: 0.0,
                borderJoinStyle: "round",
                pointHitRadius: 100,
                pointBackgroundColor: "black",
                pointBorderColor: "black",
                pointHoverBorderWidth: 8,
                data: null,
            },
        ],
    };

    // Chart Config

    const config = {
        type: "line",
        data: data,
        options: {
            scales: {
                x: {
                    offset: true,
                    ticks: {
                        display: false
                              },
                    grid: {
                        display: false,
                        drawBorder: false,
                        drawOnChartArea: false,
                        drawTicks: false,
                    },
                },
                y: {
                    ticks: {
                        display: false
                              },
                    grid: {
                        display: true,
                        drawBorder: false,
                        drawOnChartArea: false,
                        drawTicks: false,

                    },
                },
            },
            plugins: {
                legend: {
                    display: false,
                },
                tooltip: {
                    backgroundColor: "white",
                    borderColor: "rgba(193, 193, 193, .5)",
                    borderWidth: 2,
                    titleColor: "rgb(197, 0, 51)",
                    titleAlign: "center",
                    bodyAlign: "center",
                    displayColors: false,
                    bodyColor: "grey",
                    callbacks: {
                        title: function (context) {
                            return (
                                context[0].label +
                                " " +
                                context[0].dataset.label
                            );
                        },
                        label: function (tooltipItem, data) {
                            var value =
                                myChart.data.datasets[tooltipItem.datasetIndex]
                                    .data[tooltipItem.dataIndex];

                            return value;
                        },
                    },
                },
            },
        },
    };

    // One Year Button

    function onBtnMonateClick() {
        console.log("onBtnMonateClick");
        // 👇️ hide button
        listOne.style.display = "";
        listTwo.style.display = "";
        listMonthOne.style.display = "none";
        listMonthTwo.style.display = "none";
        data.datasets[0].label = "2022";
        data.datasets[1].label = "";
        data.datasets[0].lineTension = 0.3;
        data.datasets[1].lineTension = 0.3;

        data.datasets[0].data = YearDatasets[YearDatasets.length - 1].umsätze;

        data.datasets[1].data = "";

        data.labels = labelYear;

        myChart.update();
    }

    // One Month Button

    function onBtnTageClick() {
        //  hide button
        listOne.style.display = "none";
        listTwo.style.display = "none";
        listMonthOne.style.display = "";
        listMonthTwo.style.display = "";
        data.datasets[1].label = "";
        data.datasets[0].lineTension = 0.3;
        data.datasets[1].lineTension = 0.3;
        data.datasets[0].label = listMonthOne.options[listMonthOne.selectedIndex].text;

        //data.labels = YearDatasets[0].daysInMonth.Januar;
        data.labels = [
            "1",
            "2",
            "3",
            "4",
            "5",
            "6",
            "7",
            "8",
            "9",
            "10",
            "11",
            "12",
            "13",
            "14",
            "15",
            "16",
            "17",
            "18",
            "19",
            "20",
            "21",
            "22",
            "23",
            "24",
            "25",
            "26",
            "27",
            "28",
            "29",
            "30",
            "31",
        ];
        data.datasets[0].data = YearDatasets[YearDatasets.length - 1].umsätzeMonths.August;
        data.datasets[1].data = "";

        myChart.update();
    }

    // Switch to Bar Chart

    function onBtnBarClick() {
        //  hide button
        btnBar.style.display = "none";
        btnLine.style.display = "";
        config.type = "bar";

        data.datasets[0].backgroundColor = gradientBar;
        data.datasets[1].backgroundColor = gradientTwoBar;

        myChart.update();
    }

    // Switch to Line Chart

    function onBtnLineClick() {
        //  hide button
        btnBar.style.display = "";
        btnLine.style.display = "none";
        config.type = "line";

        data.datasets[0].backgroundColor = gradient;
        data.datasets[1].backgroundColor = gradientTwo;

        myChart.update();
    }

    // change data with dropdown menu

    function changeDataOne() {
        data.datasets[0].data = listOne.value.split(",");

        data.datasets[0].label = listOne.options[listOne.selectedIndex].text;

        myChart.update();
    }

    function changeDataTwo() {
        data.datasets[1].data = listTwo.value.split(",");

        data.datasets[1].label = listTwo.options[listTwo.selectedIndex].text;

        myChart.update();
    }

    function changeDataMonthOne() {
        data.datasets[0].data = listMonthOne.value.split(",");

        data.datasets[0].label =
            listMonthOne.options[listMonthOne.selectedIndex].text;

        myChart.update();
    }

    function changeDataMonthTwo() {
        data.datasets[1].data = listMonthTwo.value.split(",");

        data.datasets[1].label =
            listMonthTwo.options[listMonthTwo.selectedIndex].text;

        myChart.update();
    }

    function changeChartColor() {
        if (this.checked) {
            data.datasets[0].backgroundColor = "rgba(197, 0, 51, .2)";

            data.datasets[1].backgroundColor = "rgba(130, 130, 130, .6)";

            data.datasets[1].borderColor = "rgb(130, 130, 130)";

            data.datasets[0].borderColor = "rgba(197, 0, 51, .2)";

            myChart.update();
        } else {
            data.datasets[0].backgroundColor = gradient;

            data.datasets[1].backgroundColor = gradientTwo;

            data.datasets[1].borderColor = "rgb(132, 132, 132)";

            data.datasets[0].borderColor = "rgb(197, 0, 51)";

            myChart.update();
        }
    }

    onMount(() => {
        var daysJanuar = getDaysInMonth(0, 2020);

        ctx = canvas.getContext("2d");

        // Gradient

        gradient = ctx.createLinearGradient(0, 0, 0, 190);
        data.datasets[0].backgroundColor = gradient;

        // color stops
        gradient.addColorStop(0.3, "rgba(197, 0, 51, .2)");
        gradient.addColorStop(0.9, "transparent");

        gradientTwo = ctx.createLinearGradient(0, 0, 0, 300);
        data.datasets[1].backgroundColor = gradientTwo;

        // color stops
        gradientTwo.addColorStop(0.3, "rgba(214, 214, 214, .4)");
        gradientTwo.addColorStop(0.9, "transparent");

        gradientBar = ctx.createLinearGradient(0, 0, 0, 350);

        // color stops
        gradientBar.addColorStop(0.3, "rgba(197, 0, 51, .6)");
        gradientBar.addColorStop(1, "white");

        gradientTwoBar = ctx.createLinearGradient(0, 0, 0, 350);

        // color stops
        gradientTwoBar.addColorStop(0.3, "rgba(110, 110, 110, .9)");
        gradientTwoBar.addColorStop(1, "lightgrey");

        // chart building
        myChart = new Chart(ctx, config);

        return () => {};
    });
</script>

<head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
        href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/css/bootstrap.min.css"
        rel="stylesheet"
        integrity="sha384-gH2yIJqKdNHPEq0n4Mqa/HGKIhSkIHeL5AyhkYV8i59U5AR6csBvApHHNl/vI1Bx"
        crossorigin="anonymous"
    />
    <title>Vite + Svelte + TS</title>

    <script
        src="//ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>

    <script
        src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-A3rJD856KowSb7dwlZdYEkO39Gagi7vIsF0jrRAoQmDKKtQBHUuLZ9AsSv4jD4Xa"
        crossorigin="anonymous"></script>

    <script
        src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js"></script>
</head>

<!-- Überschrift + Profilbild -->
<div class="mb-4 mt-4 d-flex justify-content-between align-items-center">
    <h1 style="" class="fs-3 ms-4">Willkommen zurück, Cosimo!</h1>

    <img
        src="https://cdn.glitch.global/0c15c725-e764-4776-a32b-28fdb0e82a47/pngwing.com%20(4).png?v=1656781464561"
        class="rounded-circle me-4"
        alt="Cinque Terre"
        style="width:5%; "
    />
</div>

<!-- Card -->
<div class="card mb-3 shadow">
    <div class="card-body">
        <div>
            <div>
                <style>
                </style>

<div class="d-flex justify-content-between align-items-baseline mb-1 ">

<h1 class="d-flex flex-row fs-5 text text-muted ms-2">
    Aktuelles Saldo
</h1>

<h1 class="fs-5 text text-muted me-2">{formatted_date}</h1>

</div>

<div
    class="d-flex justify-content-between align-items-baseline mb-3 "
>
    <h1 class="fs-3 ms-2">
        {YearDatasets[YearDatasets.length - 1].umsätze[
            YearDatasets[YearDatasets.length - 1].umsätze
                .length - 1
        ]}€
    </h1>

</div>

                <canvas
                    bind:this={canvas}
                    width={"30vw"}
                    height={"10vh"}
                    class="ms-1 me-1"
                />

                <div
                    class="btn-group btn-group-sm mx-auto mt-2"
                    role="group"
                    aria-label="Basic radio toggle button group"
                >
                    <input
                        type="radio"
                        class="btn-check"
                        name="btnradio"
                        id="btnMonate"
                        bind:this={btnMonate}
                        autocomplete="off"
                        checked
                    />
                    <label
                        class="btn btn-outline-secondary shadow"
                        for="btnMonate"
                        on:click={onBtnMonateClick}>Jahr</label
                    >

                    <input
                        type="radio"
                        class="btn-check"
                        name="btnradio"
                        id="btnTage"
                        bind:this={btnTage}
                        autocomplete="off"
                    />
                    <label
                        class="btn btn-outline-secondary shadow"
                        for="btnTage"
                        on:click={onBtnTageClick}>Monat</label
                    >
                </div>
            </div>
        </div>
    </div>

    <div class="p-2 bd-highlight me-5" style="display: none;">
        <select
            bind:this={listOne}
            on:change={changeDataOne}
            class="selectbox btn btn-secondary shadow me-2"
        >
            <option value={YearDatasets[4].umsätze} id="2022">2022</option>
            <option value={YearDatasets[3].umsätze} id="2021">2021</option>
            <option value={YearDatasets[2].umsätze} id="2020">2020</option>
            <option value={YearDatasets[1].umsätze} id="2019">2019</option>
            <option value={YearDatasets[0].umsätze} id="2018">2018</option>
            <option value="null" id="none">Hidden</option>
        </select>

        <select
            bind:this={listTwo}
            on:change={changeDataTwo}
            class="selectbox btn btn-secondary shadow"
        >
            <option value="" id="none">2. Jahr</option>
            <option value={YearDatasets[4].umsätze} id="2022">2022</option>
            <option value={YearDatasets[3].umsätze} id="2021">2021</option>
            <option value={YearDatasets[2].umsätze} id="2020">2020</option>
            <option value={YearDatasets[1].umsätze} id="2019">2019</option>
            <option value={YearDatasets[0].umsätze} id="2018">2018</option>
            <option value="null" id="none">Hidden</option>
        </select>

        <!-- Monate Dropdowns -->
        <select
            bind:this={listMonthOne}
            on:change={changeDataMonthOne}
            style="display:none"
            class="selectbox btn btn-secondary shadow me-2"
        >
           
            <option value={YearDatasets[4].umsätzeMonths.August} id="2020"
                >August 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.September} id="2019"
                >September 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.Oktober} id="2018"
                >Oktober 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.November} id="2022"
                >November 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.Dezember} id="2021"
                >Dezember 2022</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Januar} id="2022"
                >Januar 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Februar} id="2021"
                >Februar 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.März} id="2020"
                >März 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.April} id="2019"
                >April 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Mai} id="2018"
                >Mai 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Juni} id="2022"
                >Juni 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Juli} id="2021"
                >Juli 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.August} id="2020"
                >August 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.September} id="2019"
                >September 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Oktober} id="2018"
                >Oktober 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.November} id="2022"
                >November 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Dezember} id="2021"
                >Dezember 2021</option
            >
            <option value="null" id="none">Hidden</option>
        </select>

        <select
            bind:this={listMonthTwo}
            on:change={changeDataMonthTwo}
            style="display:none"
            class="selectbox btn btn-secondary shadow"
        >
            <option value="null" id="none">2. Monat</option>
            <option value={YearDatasets[4].umsätzeMonths.Januar} id="2022"
                >Januar 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.Februar} id="2021"
                >Februar 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.März} id="2020"
                >März 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.April} id="2019"
                >April 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.Mai} id="2018"
                >Mai 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.Juni} id="2022"
                >Juni 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.Juli} id="2021"
                >Juli 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.August} id="2020"
                >August 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.September} id="2019"
                >September 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.Oktober} id="2018"
                >Oktober 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.November} id="2022"
                >November 2022</option
            >
            <option value={YearDatasets[4].umsätzeMonths.Dezember} id="2021"
                >Dezember 2022</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Januar} id="2022"
                >Januar 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Februar} id="2021"
                >Februar 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.März} id="2020"
                >März 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.April} id="2019"
                >April 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Mai} id="2018"
                >Mai 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Juni} id="2022"
                >Juni 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Juli} id="2021"
                >Juli 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.August} id="2020"
                >August 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.September} id="2019"
                >September 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Oktober} id="2018"
                >Oktober 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.November} id="2022"
                >November 2021</option
            >
            <option value={YearDatasets[3].umsätzeMonths.Dezember} id="2021"
                >Dezember 2021</option
            >
        </select>
    </div>
    <script
        src="//ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>
    <script
        src="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0/dist/js/bootstrap.bundle.min.js"
        integrity="sha384-A3rJD856KowSb7dwlZdYEkO39Gagi7vIsF0jrRAoQmDKKtQBHUuLZ9AsSv4jD4Xa"
        crossorigin="anonymous"></script>
    <script
        src="https://cdn.jsdelivr.net/npm/@popperjs/core@2.9.2/dist/umd/popper.min.js"></script>

    <script defer src="/build/bundle.js"></script>
</div>
