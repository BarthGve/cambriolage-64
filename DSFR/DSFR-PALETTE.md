# DSFR - Palette de Couleurs Officielle

> **Système de Design de l'État** - Version 2025  
> Documentation des couleurs officielles pour le gouvernement français

## 🎨 Vue d'ensemble

La palette DSFR est issue de la Marque de l'État créée en 2017 pour harmoniser et renforcer la reconnaissance de la parole de l'État. Elle comprend 24 couleurs réparties en 4 familles avec un système d'accessibilité optimisé.

## 📐 Système de couleurs

### Principe d'accessibilité
- **Indice de luminosité** : Basé sur le modèle HSL (Hue, Saturation, Lightness)
- **Contraste garanti** : Écart de 500 entre deux couleurs = ratio de contraste ≥ 4,5:1
- **Exemple** : Bleu France (indice 113) accessible sur fond d'indice 613+

---

## 🔵 Couleurs Primaires

### Bleu France - Thème Clair
```css
/* Couleur principale de l'État */
--bleu-france-main-525: #6a6af4;       /* rgb(106,106,244) hsl(240deg 85.8% 68.5%) */
--bleu-france-main-525-hover: #9898f8; /* hover rgb(152,152,248) */
--bleu-france-main-525-active: #aeaef9; /* active rgb(174,174,249) */

--bleu-france-sun-113: #000091;        /* rgb(0,0,145) hsl(240deg 100% 28.4%) */
--bleu-france-sun-113-hover: #1212ff;  /* hover rgb(18,18,255) */
--bleu-france-sun-113-active: #2323ff; /* active rgb(35,35,255) */

/* Teintes claires */
--bleu-france-975: #f5f5fe;            /* rgb(245,245,254) hsl(240deg 86.3% 98%) */
--bleu-france-975-hover: #dcdcfc;      /* hover rgb(220,220,252) */
--bleu-france-975-active: #cbcbfa;     /* active rgb(203,203,250) */

--bleu-france-950: #ececfe;            /* rgb(236,236,254) hsl(240deg 86.4% 96.1%) */
--bleu-france-950-hover: #cecefc;      /* hover rgb(206,206,252) */
--bleu-france-950-active: #bbbbfc;     /* active rgb(187,187,252) */

--bleu-france-925: #e3e3fd;            /* rgb(227,227,253) hsl(240deg 86.5% 94.2%) */
--bleu-france-925-hover: #c1c1fb;      /* hover rgb(193,193,251) */
--bleu-france-925-active: #adadf9;     /* active rgb(173,173,249) */

--bleu-france-850: #cacafb;            /* rgb(202,202,251) hsl(240deg 86.8% 88.8%) */
--bleu-france-850-hover: #a1a1f8;      /* hover rgb(161,161,248) */
--bleu-france-850-active: #8b8bf6;     /* active rgb(139,139,246) */
```

### Bleu France - Thème Sombre
```css
--bleu-france-main-525: #6a6af4;       /* rgb(106,106,244) hsl(240deg 85.8% 68.5%) */
--bleu-france-main-525-hover: #9898f8; /* hover rgb(152,152,248) */
--bleu-france-main-525-active: #aeaef9; /* active rgb(174,174,249) */

--bleu-france-625: #8585f6;            /* rgb(133,133,246) hsl(240deg 86.5% 74.4%) */
--bleu-france-625-hover: #b1b1f9;      /* hover rgb(177,177,249) */
--bleu-france-625-active: #c6c6fb;     /* active rgb(198,198,251) */

/* Teintes foncées */
--bleu-france-200: #313178;            /* rgb(49,49,120) hsl(240deg 41.8% 33.1%) */
--bleu-france-200-hover: #5757ad;      /* hover rgb(87,87,173) */
--bleu-france-200-active: #6c6cbb;     /* active rgb(108,108,187) */

--bleu-france-125: #272747;            /* rgb(39,39,71) hsl(240deg 29.8% 21.6%) */
--bleu-france-125-hover: #4a4a7d;      /* hover rgb(74,74,125) */
--bleu-france-125-active: #5e5e90;     /* active rgb(94,94,144) */

--bleu-france-100: #21213f;            /* rgb(33,33,63) hsl(240deg 30.7% 18.8%) */
--bleu-france-100-hover: #424275;      /* hover rgb(66,66,117) */
--bleu-france-100-active: #56568c;     /* active rgb(86,86,140) */

--bleu-france-75: #1b1b35;             /* rgb(27,27,53) hsl(240deg 32.1% 15.7%) */
--bleu-france-75-hover: #3a3a68;       /* hover rgb(58,58,104) */
--bleu-france-75-active: #4d4d83;      /* active rgb(77,77,131) */
```

### Rouge Marianne - Thème Clair
```css
/* Couleur secondaire officielle */
--rouge-marianne-main-472: #e1000f;    /* rgb(225,0,15) hsl(356deg 100% 44.1%) */
--rouge-marianne-main-472-hover: #ff292f; /* hover rgb(255,41,47) */
--rouge-marianne-main-472-active: #ff4347; /* active rgb(255,67,71) */

--rouge-marianne-425: #c9191e;         /* rgb(201,25,30) hsl(358.1deg 78% 44.3%) */
--rouge-marianne-425-hover: #f93f42;   /* hover rgb(249,63,66) */
--rouge-marianne-425-active: #f95a5c;  /* active rgb(249,90,92) */

/* Teintes claires */
--rouge-marianne-975: #fef4f4;         /* rgb(254,244,244) hsl(359.6deg 88.3% 97.7%) */
--rouge-marianne-975-hover: #fcd7d7;   /* hover rgb(252,215,215) */
--rouge-marianne-975-active: #fac4c4;  /* active rgb(250,196,196) */

--rouge-marianne-950: #fee9e9;         /* rgb(254,233,233) hsl(359.6deg 88.6% 95.4%) */
--rouge-marianne-950-hover: #fdc5c5;   /* hover rgb(253,197,197) */
--rouge-marianne-950-active: #fcafaf;  /* active rgb(252,175,175) */

--rouge-marianne-925: #fddede;         /* rgb(253,222,222) hsl(359.6deg 88.9% 93.2%) */
--rouge-marianne-925-hover: #fbb6b6;   /* hover rgb(251,182,182) */
--rouge-marianne-925-active: #fa9e9e;  /* active rgb(250,158,158) */

--rouge-marianne-850: #fcbfbf;         /* rgb(252,191,191) hsl(359.5deg 89.9% 86.7%) */
--rouge-marianne-850-hover: #fb8f8f;   /* hover rgb(251,143,143) */
--rouge-marianne-850-active: #fa7474;  /* active rgb(250,116,116) */
```

### Rouge Marianne - Thème Sombre
```css
--rouge-marianne-main-472: #e1000f;    /* rgb(225,0,15) hsl(356deg 100% 44.1%) */
--rouge-marianne-main-472-hover: #ff292f; /* hover rgb(255,41,47) */
--rouge-marianne-main-472-active: #ff4347; /* active rgb(255,67,71) */

--rouge-marianne-625: #f95c5e;         /* rgb(249,92,94) hsl(359.2deg 92.8% 66.8%) */
--rouge-marianne-625-hover: #fa9293;   /* hover rgb(250,146,147) */
--rouge-marianne-625-active: #fbabac;  /* active rgb(251,171,172) */

/* Teintes foncées */
--rouge-marianne-200: #5e2a2b;         /* rgb(94,42,43) hsl(359.4deg 38% 26.6%) */
--rouge-marianne-200-hover: #9c4a4c;   /* hover rgb(156,74,76) */
--rouge-marianne-200-active: #be5c5e;  /* active rgb(190,92,94) */

--rouge-marianne-125: #3b2424;         /* rgb(59,36,36) hsl(359.5deg 24.1% 18.6%) */
--rouge-marianne-125-hover: #6b4545;   /* hover rgb(107,69,69) */
--rouge-marianne-125-active: #865757;  /* active rgb(134,87,87) */

--rouge-marianne-100: #331f1f;         /* rgb(51,31,31) hsl(359.5deg 25% 16.1%) */
--rouge-marianne-100-hover: #613f3f;   /* hover rgb(97,63,63) */
--rouge-marianne-100-active: #7b5151;  /* active rgb(123,81,81) */

--rouge-marianne-75: #2b1919;          /* rgb(43,25,25) hsl(359.5deg 26.3% 13.3%) */
--rouge-marianne-75-hover: #573737;    /* hover rgb(87,55,55) */
--rouge-marianne-75-active: #704848;   /* active rgb(112,72,72) */
```

### Blanc
```css
/* Blanc officiel */
--blanc: #FFFFFF;
--blanc-rgb: rgb(255, 255, 255);
--blanc-hsl: hsl(0, 0%, 100%);
```

---

## ⚪ Couleurs Neutres

### Thème Clair
```css
/* Gris principal */
--grey-main-525: #7b7b7b;              /* rgb(123,123,123) hsl(0deg 0% 48.2%) */
--grey-main-525-hover: #a6a6a6;        /* hover rgb(166,166,166) */
--grey-main-525-active: #bababa;       /* active rgb(186,186,186) */

--grey-425: #666666;                   /* rgb(102,102,102) hsl(0deg 0% 40%) */
--grey-425-hover: #919191;             /* hover rgb(145,145,145) */
--grey-425-active: #a6a6a6;            /* active rgb(166,166,166) */

/* Gris clairs */
--grey-1000: #ffffff;                  /* rgb(255,255,255) hsl(0deg 0% 100%) */
--grey-1000-hover: #f6f6f6;            /* hover rgb(246,246,246) */
--grey-1000-active: #ededed;           /* active rgb(237,237,237) */

--grey-975: #f6f6f6;                   /* rgb(246,246,246) hsl(0deg 0% 96.5%) */
--grey-975-hover: #dfdfdf;             /* hover rgb(223,223,223) */
--grey-975-active: #cfcfcf;            /* active rgb(207,207,207) */

--grey-950: #eeeeee;                   /* rgb(238,238,238) hsl(0deg 0% 93.3%) */
--grey-950-hover: #d2d2d2;             /* hover rgb(210,210,210) */
--grey-950-active: #c1c1c1;            /* active rgb(193,193,193) */

--grey-925: #e5e5e5;                   /* rgb(229,229,229) hsl(0deg 0% 89.8%) */
--grey-925-hover: #c5c5c5;             /* hover rgb(197,197,197) */
--grey-925-active: #b2b2b2;            /* active rgb(178,178,178) */

--grey-900: #dddddd;                   /* rgb(221,221,221) hsl(0deg 0% 86.7%) */
--grey-900-hover: #bbbbbb;             /* hover rgb(187,187,187) */
--grey-900-active: #a7a7a7;            /* active rgb(167,167,167) */

--grey-850: #cecece;                   /* rgb(206,206,206) hsl(0deg 0% 80.8%) */
--grey-850-hover: #a8a8a8;             /* hover rgb(168,168,168) */
--grey-850-active: #939393;            /* active rgb(147,147,147) */
```

### Thème Sombre
```css
/* Gris principal (identique) */
--grey-main-525: #7b7b7b;              /* rgb(123,123,123) hsl(0deg 0% 48.2%) */
--grey-main-525-hover: #a6a6a6;        /* hover rgb(166,166,166) */
--grey-main-525-active: #bababa;       /* active rgb(186,186,186) */

--grey-625: #929292;                   /* rgb(146,146,146) hsl(0deg 0% 57.3%) */
--grey-625-hover: #bbbbbb;             /* hover rgb(187,187,187) */
--grey-625-active: #cecece;            /* active rgb(206,206,206) */

/* Gris foncés */
--grey-200: #3a3a3a;                   /* rgb(58,58,58) hsl(0deg 0% 22.7%) */
--grey-200-hover: #616161;             /* hover rgb(97,97,97) */
--grey-200-active: #777777;            /* active rgb(119,119,119) */

--grey-175: #353535;                   /* rgb(53,53,53) hsl(0deg 0% 20.8%) */
--grey-175-hover: #5c5c5c;             /* hover rgb(92,92,92) */
--grey-175-active: #717171;            /* active rgb(113,113,113) */

--grey-150: #2f2f2f;                   /* rgb(47,47,47) hsl(0deg 0% 18.4%) */
--grey-150-hover: #545454;             /* hover rgb(84,84,84) */
--grey-150-active: #696969;            /* active rgb(105,105,105) */

--grey-125: #2a2a2a;                   /* rgb(42,42,42) hsl(0deg 0% 16.5%) */
--grey-125-hover: #4e4e4e;             /* hover rgb(78,78,78) */
--grey-125-active: #636363;            /* active rgb(99,99,99) */

--grey-100: #242424;                   /* rgb(36,36,36) hsl(0deg 0% 14.1%) */
--grey-100-hover: #474747;             /* hover rgb(71,71,71) */
--grey-100-active: #5b5b5b;            /* active rgb(91,91,91) */

--grey-75: #1e1e1e;                    /* rgb(30,30,30) hsl(0deg 0% 11.8%) */
--grey-75-hover: #3f3f3f;              /* hover rgb(63,63,63) */
--grey-75-active: #525252;             /* active rgb(82,82,82) */

--grey-50: #161616;                    /* rgb(22,22,22) hsl(0deg 0% 8.6%) */
--grey-50-hover: #343434;              /* hover rgb(52,52,52) */
--grey-50-active: #474747;             /* active rgb(71,71,71) */
```

---

## 🚨 Couleurs Système

### Info - Thème Clair
```css
/* Information principale */
--info-main-525: #0078f3;              /* rgb(0,120,243) hsl(210.4deg 100% 47.6%) */
--info-main-525-hover: #6196ff;        /* hover rgb(97,150,255) */
--info-main-525-active: #85a9ff;       /* active rgb(133,169,255) */

--info-425: #0063cb;                   /* rgb(0,99,203) hsl(210.8deg 100% 39.8%) */
--info-425-hover: #3b87ff;             /* hover rgb(59,135,255) */
--info-425-active: #6798ff;            /* active rgb(103,152,255) */

/* Teintes claires */
--info-975: #f4f6ff;                   /* rgb(244,246,255) hsl(227.2deg 100% 97.8%) */
--info-975-hover: #d6deff;             /* hover rgb(214,222,255) */
--info-975-active: #c2cfff;            /* active rgb(194,207,255) */

--info-950: #e8edff;                   /* rgb(232,237,255) hsl(226.9deg 100% 95.5%) */
--info-950-hover: #c2d1ff;             /* hover rgb(194,209,255) */
--info-950-active: #a9bfff;            /* active rgb(169,191,255) */

--info-925: #dde5ff;                   /* rgb(221,229,255) hsl(226.5deg 100% 93.4%) */
--info-925-hover: #b1c6ff;             /* hover rgb(177,198,255) */
--info-925-active: #95b4ff;            /* active rgb(149,180,255) */

--info-850: #bccdff;                   /* rgb(188,205,255) hsl(225.3deg 100% 86.9%) */
--info-850-hover: #83a9ff;             /* hover rgb(131,169,255) */
--info-850-active: #5f96ff;            /* active rgb(95,150,255) */
```

### Info - Thème Sombre
```css
--info-main-525: #0078f3;              /* rgb(0,120,243) hsl(210.4deg 100% 47.6%) */
--info-main-525-hover: #6196ff;        /* hover rgb(97,150,255) */
--info-main-525-active: #85a9ff;       /* active rgb(133,169,255) */

--info-625: #518fff;                   /* rgb(81,143,255) hsl(218.7deg 100% 65.9%) */
--info-625-hover: #98b4ff;             /* hover rgb(152,180,255) */
--info-625-active: #b4c7ff;            /* active rgb(180,199,255) */

/* Teintes foncées */
--info-200: #273961;                   /* rgb(39,57,97) hsl(221.4deg 42.4% 26.6%) */
--info-200-hover: #45619f;             /* hover rgb(69,97,159) */
--info-200-active: #5576c0;            /* active rgb(85,118,192) */

--info-125: #222a3f;                   /* rgb(34,42,63) hsl(223.7deg 30.2% 18.9%) */
--info-125-hover: #414e71;             /* hover rgb(65,78,113) */
--info-125-active: #53638d;            /* active rgb(83,99,141) */

--info-100: #1d2437;                   /* rgb(29,36,55) hsl(223.7deg 31.3% 16.3%) */
--info-100-hover: #3b4767;             /* hover rgb(59,71,103) */
--info-100-active: #4c5b83;            /* active rgb(76,91,131) */

--info-75: #171d2e;                    /* rgb(23,29,46) hsl(223.7deg 32.9% 13.6%) */
--info-75-hover: #333e5c;              /* hover rgb(51,62,92) */
--info-75-active: #445177;             /* active rgb(68,81,119) */
```

### Succès - Thème Clair
```css
/* Succès principal */
--success-main-525: #1f8d49;           /* rgb(31,141,73) hsl(143deg 63.5% 33.8%) */
--success-main-525-hover: #2ec166;     /* hover rgb(46,193,102) */
--success-main-525-active: #36db75;    /* active rgb(54,219,117) */

--success-425: #18753c;                /* rgb(24,117,60) hsl(143deg 65.5% 27.7%) */
--success-425-hover: #27a959;          /* hover rgb(39,169,89) */
--success-425-active: #2fc368;         /* active rgb(47,195,104) */

/* Teintes claires */
--success-975: #dffee6;                /* rgb(223,254,230) hsl(133.6deg 96% 93.5%) */
--success-975-hover: #8afcab;          /* hover rgb(138,252,171) */
--success-975-active: #4efb8d;         /* active rgb(78,251,141) */

--success-950: #b8fec9;                /* rgb(184,254,201) hsl(135deg 96.5% 85.8%) */
--success-950-hover: #46fd89;          /* hover rgb(70,253,137) */
--success-950-active: #34eb7b;         /* active rgb(52,235,123) */

--success-925: #88fdaa;                /* rgb(136,253,170) hsl(137.4deg 97.1% 76.3%) */
--success-925-hover: #3ee87e;          /* hover rgb(62,232,126) */
--success-925-active: #36d070;         /* active rgb(54,208,112) */

--success-850: #3bea7e;                /* rgb(59,234,126) hsl(143deg 80.9% 57.5%) */
--success-850-hover: #2cb862;          /* hover rgb(44,184,98) */
--success-850-active: #259e53;         /* active rgb(37,158,83) */
```

### Succès - Thème Sombre
```css
--success-main-525: #1f8d49;           /* rgb(31,141,73) hsl(143deg 63.5% 33.8%) */
--success-main-525-hover: #2ec166;     /* hover rgb(46,193,102) */
--success-main-525-active: #36db75;    /* active rgb(54,219,117) */

--success-625: #27a658;                /* rgb(39,166,88) hsl(143deg 62.1% 40.2%) */
--success-625-hover: #36d975;          /* hover rgb(54,217,117) */
--success-625-active: #3df183;         /* active rgb(61,241,131) */

/* Teintes foncées */
--success-200: #204129;                /* rgb(32,65,41) hsl(137deg 33.2% 19%) */
--success-200-hover: #3a6d48;          /* hover rgb(58,109,72) */
--success-200-active: #478558;         /* active rgb(71,133,88) */

--success-125: #1e2e22;                /* rgb(30,46,34) hsl(135.1deg 21.4% 14.8%) */
--success-125-hover: #3b5541;          /* hover rgb(59,85,65) */
--success-125-active: #4b6b53;         /* active rgb(75,107,83) */

--success-100: #19271d;                /* rgb(25,39,29) hsl(135.1deg 22.4% 12.6%) */
--success-100-hover: #344c3b;          /* hover rgb(52,76,59) */
--success-100-active: #44624d;         /* active rgb(68,98,77) */

--success-75: #142117;                 /* rgb(20,33,23) hsl(135.1deg 23.9% 10.3%) */
--success-75-hover: #2e4533;           /* hover rgb(46,69,51) */
--success-75-active: #3d5943;          /* active rgb(61,89,67) */
```

### Avertissement - Thème Clair
```css
/* Avertissement principal */
--warning-main-525: #d64d00;           /* rgb(214,77,0) hsl(21.7deg 100% 42%) */
--warning-main-525-hover: #ff754e;     /* hover rgb(255,117,78) */
--warning-main-525-active: #ff8e76;    /* active rgb(255,142,118) */

--warning-425: #b34000;                /* rgb(179,64,0) hsl(21.3deg 100% 35.1%) */
--warning-425-hover: #ff6218;          /* hover rgb(255,98,24) */
--warning-425-active: #ff7a55;         /* active rgb(255,122,85) */

/* Teintes claires */
--warning-975: #fff4f3;                /* rgb(255,244,243) hsl(6.9deg 100% 97.6%) */
--warning-975-hover: #ffd7d3;          /* hover rgb(255,215,211) */
--warning-975-active: #ffc4bd;         /* active rgb(255,196,189) */

--warning-950: #ffe9e6;                /* rgb(255,233,230) hsl(7.1deg 100% 95.1%) */
--warning-950-hover: #ffc6bd;          /* hover rgb(255,198,189) */
--warning-950-active: #ffb0a2;         /* active rgb(255,176,162) */

--warning-925: #ffded9;                /* rgb(255,222,217) hsl(7.4deg 100% 92.6%) */
--warning-925-hover: #ffb6a9;          /* hover rgb(255,182,169) */
--warning-925-active: #ff9f8b;         /* active rgb(255,159,139) */

--warning-850: #ffbeb4;                /* rgb(255,190,180) hsl(8.3deg 100% 85.2%) */
--warning-850-hover: #ff8e77;          /* hover rgb(255,142,119) */
--warning-850-active: #ff7550;         /* active rgb(255,117,80) */
```

### Avertissement - Thème Sombre
```css
--warning-main-525: #d64d00;           /* rgb(214,77,0) hsl(21.7deg 100% 42%) */
--warning-main-525-hover: #ff754e;     /* hover rgb(255,117,78) */
--warning-main-525-active: #ff8e76;    /* active rgb(255,142,118) */

--warning-625: #fc5d00;                /* rgb(252,93,0) hsl(22.1deg 100% 49.4%) */
--warning-625-hover: #ff8c73;          /* hover rgb(255,140,115) */
--warning-625-active: #ffa595;         /* active rgb(255,165,149) */

/* Teintes foncées */
--warning-200: #5d2c20;                /* rgb(93,44,32) hsl(11.6deg 48.2% 24.5%) */
--warning-200-hover: #9a4d3a;          /* hover rgb(154,77,58) */
--warning-200-active: #bc5f49;         /* active rgb(188,95,73) */

--warning-125: #3e231e;                /* rgb(62,35,30) hsl(9.7deg 35.5% 18%) */
--warning-125-hover: #70433b;          /* hover rgb(112,67,59) */
--warning-125-active: #8d564c;         /* active rgb(141,86,76) */

--warning-100: #361e19;                /* rgb(54,30,25) hsl(9.7deg 36.8% 15.5%) */
--warning-100-hover: #663d35;          /* hover rgb(102,61,53) */
--warning-100-active: #824f44;         /* active rgb(130,79,68) */

--warning-75: #2d1814;                 /* rgb(45,24,20) hsl(9.7deg 38.8% 12.8%) */
--warning-75-hover: #5b352e;           /* hover rgb(91,53,46) */
--warning-75-active: #75473e;          /* active rgb(117,71,62) */
```

### Erreur - Thème Clair
```css
/* Erreur principale */
--error-main-525: #f60700;             /* rgb(246,7,0) hsl(1.8deg 100% 48.2%) */
--error-main-525-hover: #ff3634;       /* hover rgb(255,54,52) */
--error-main-525-active: #ff5150;      /* active rgb(255,81,80) */

--error-425: #ce0500;                  /* rgb(206,5,0) hsl(1.4deg 100% 40.4%) */
--error-425-hover: #ff2725;            /* hover rgb(255,39,37) */
--error-425-active: #ff4140;           /* active rgb(255,65,64) */

/* Teintes claires */
--error-975: #fff4f4;                  /* rgb(255,244,244) hsl(0.1deg 100% 97.8%) */
--error-975-hover: #ffd7d7;            /* hover rgb(255,215,215) */
--error-975-active: #ffc3c3;           /* active rgb(255,195,195) */

--error-950: #ffe9e9;                  /* rgb(255,233,233) hsl(0.2deg 100% 95.6%) */
--error-950-hover: #ffc5c5;            /* hover rgb(255,197,197) */
--error-950-active: #ffafaf;           /* active rgb(255,175,175) */

--error-925: #ffdddd;                  /* rgb(255,221,221) hsl(0.2deg 100% 93.4%) */
--error-925-hover: #ffb4b4;            /* hover rgb(255,180,180) */
--error-925-active: #ff9c9c;           /* active rgb(255,156,156) */

--error-850: #ffbdbd;                  /* rgb(255,189,189) hsl(0.2deg 100% 87.1%) */
--error-850-hover: #ff8c8c;            /* hover rgb(255,140,140) */
--error-850-active: #ff7272;           /* active rgb(255,114,114) */
```

### Erreur - Thème Sombre
```css
--error-main-525: #f60700;             /* rgb(246,7,0) hsl(1.8deg 100% 48.2%) */
--error-main-525-hover: #ff3634;       /* hover rgb(255,54,52) */
--error-main-525-active: #ff5150;      /* active rgb(255,81,80) */

--error-625: #ff5655;                  /* rgb(255,86,85) hsl(0.4deg 100% 66.6%) */
--error-625-hover: #ff8c8c;            /* hover rgb(255,140,140) */
--error-625-active: #ffa6a6;           /* active rgb(255,166,166) */

/* Teintes foncées */
--error-200: #642626;                  /* rgb(100,38,38) hsl(0.3deg 45.2% 26.9%) */
--error-200-hover: #a74545;            /* hover rgb(167,69,69) */
--error-200-active: #cb5555;           /* active rgb(203,85,85) */

--error-125: #412121;                  /* rgb(65,33,33) hsl(0.2deg 32.5% 19.2%) */
--error-125-hover: #764040;            /* hover rgb(118,64,64) */
--error-125-active: #935252;           /* active rgb(147,82,82) */

--error-100: #391c1c;                  /* rgb(57,28,28) hsl(0.2deg 33.6% 16.6%) */
--error-100-hover: #6c3a3a;            /* hover rgb(108,58,58) */
--error-100-active: #894b4b;           /* active rgb(137,75,75) */

--error-75: #301717;                   /* rgb(48,23,23) hsl(0.2deg 35.4% 13.8%) */
--error-75-hover: #603434;             /* hover rgb(96,52,52) */
--error-75-active: #7c4444;            /* active rgb(124,68,68) */
```

---

## 🌈 Couleurs Illustratives Complètes

### 🟢 Famille Verte

**Vert Tilleul Verveine**
```css
--tilleul-verveine-main: #B7A73F;          /* main-707 */
--tilleul-verveine-sun: #66673D;           /* sun-418 */
--tilleul-verveine-moon: #D8C634;          /* moon-817 (thème sombre) */
--tilleul-verveine-975: #FEF7DA;           /* 975 */
--tilleul-verveine-950: #FCEEAC;           /* 950 */
--tilleul-verveine-925: #FBE769;           /* 925 */
--tilleul-verveine-850: #E2CF58;           /* 850 */
```

**Vert Bourgeon**
```css
--bourgeon-main: #68A532;                  /* main-640 */
--bourgeon-sun: #447049;                   /* sun-425 */
--bourgeon-moon: #99C221;                  /* moon-759 (thème sombre) */
--bourgeon-975: #E6FEDA;                   /* 975 */
--bourgeon-950: #C9FCAC;                   /* 950 */
--bourgeon-925: #A9FB68;                   /* 925 */
--bourgeon-850: #95E257;                   /* 850 */
```

**Vert Émeraude**
```css
--emeraude-main: #00A95F;                  /* main-632 */
--emeraude-sun: #297254;                   /* sun-425 */
--emeraude-moon: #34CB6A;                  /* moon-753 (thème sombre) */
--emeraude-975: #E3FDEB;                   /* 975 */
--emeraude-950: #C3FAD5;                   /* 950 */
--emeraude-925: #9EF9BE;                   /* 925 */
--emeraude-850: #6FE49D;                   /* 850 */
```

**Vert Menthe**
```css
--menthe-main: #009081;                    /* main-548 */
--menthe-sun: #37635F;                     /* sun-373 */
--menthe-moon: #21AB8E;                    /* moon-652 (thème sombre) */
--menthe-975: #DFFDF7;                     /* 975 */
--menthe-950: #BAFAEE;                     /* 950 */
--menthe-925: #8BF8E7;                     /* 925 */
--menthe-850: #73E0CF;                     /* 850 */
```

**Vert Archipel**
```css
--archipel-main: #009099;                  /* main-557 */
--archipel-sun: #006A6F;                   /* sun-391 */
--archipel-moon: #34BAB5;                  /* moon-716 (thème sombre) */
--archipel-975: #E5FBFD;                   /* 975 */
--archipel-950: #C7F6FC;                   /* 950 */
--archipel-925: #A6F2FA;                   /* 925 */
--archipel-850: #60E0EB;                   /* 850 */
```

### 🔵 Famille Bleue

**Bleu Écume**
```css
--ecume-main: #465F9D;                     /* main-400 */
--ecume-sun: #2F4077;                      /* sun-247 */
--ecume-moon: #869ECE;                     /* moon-675 (thème sombre) */
--ecume-975: #F4F6FE;                      /* 975 */
--ecume-950: #E9EDFE;                      /* 950 */
--ecume-925: #DEE5FD;                      /* 925 */
--ecume-850: #BFCCFB;                      /* 850 */
```

**Bleu Cumulus**
```css
--cumulus-main: #417DC4;                   /* main-526 */
--cumulus-sun: #3558A2;                    /* sun-368 */
--cumulus-moon: #7AB1E8;                   /* moon-732 (thème sombre) */
--cumulus-975: #F3F6FE;                    /* 975 */
--cumulus-950: #E6EEFE;                    /* 950 */
--cumulus-925: #DAE6FD;                    /* 925 */
--cumulus-850: #B6CFFB;                    /* 850 */
```

### 🟣 Famille Violette

**Violet Glycine**
```css
--glycine-main: #A558A0;                   /* main-494 */
--glycine-sun: #6E445A;                    /* sun-319 */
--glycine-moon: #CE70CC;                   /* moon-630 (thème sombre) */
--glycine-975: #FEF3FD;                    /* 975 */
--glycine-950: #FEE7FC;                    /* 950 */
--glycine-925: #FDDBFA;                    /* 925 */
--glycine-850: #FBB8F6;                    /* 850 */
```

### 🌸 Famille Rose

**Rose Macaron**
```css
--macaron-main: #E18B76;                   /* main-689 */
--macaron-sun: #8D533E;                    /* sun-406 */
--macaron-moon: #FFB7AE;                   /* moon-833 (thème sombre) */
--macaron-975: #FEF4F2;                    /* 975 */
--macaron-950: #FEE9E6;                    /* 950 */
--macaron-925: #FDDFDA;                    /* 925 */
--macaron-850: #FCC0B4;                    /* 850 */
```

**Rose Tuile**
```css
--tuile-main: #CE614A;                     /* main-556 */
--tuile-sun: #A94645;                      /* sun-425 */
--tuile-moon: #FF9575;                     /* moon-750 (thème sombre) */
--tuile-975: #FEF4F3;                      /* 975 */
--tuile-950: #FEE9E7;                      /* 950 */
--tuile-925: #FDDFDB;                      /* 925 */
--tuile-850: #FCBFB7;                      /* 850 */
```

### 🟡 Famille Jaune/Orange

**Jaune Tournesol**
```css
--tournesol-main: #C8AA39;                 /* main-731 */
--tournesol-sun: #716043;                  /* sun-407 */
--tournesol-moon: #FFE552;                 /* moon-922 (thème sombre) */
--tournesol-975: #FEF6E3;                  /* 975 */
--tournesol-950: #FEECC2;                  /* 950 */
--tournesol-925: #FDE39C;                  /* 925 */
--tournesol-850: #EFCB3A;                  /* 850 */
```

**Jaune Moutarde**
```css
--moutarde-main: #C3992A;                  /* main-679 */
--moutarde-sun: #695240;                   /* sun-348 */
--moutarde-moon: #FFCA00;                  /* moon-860 (thème sombre) */
--moutarde-975: #FEF5E8;                   /* 975 */
--moutarde-950: #FEEBD0;                   /* 950 */
--moutarde-925: #FDE2B5;                   /* 925 */
--moutarde-850: #FCC63A;                   /* 850 */
```

**Orange Terre Battue**
```css
--terre-battue-main: #E4794A;              /* main-645 */
--terre-battue-sun: #755348;               /* sun-370 */
--terre-battue-moon: #FF732C;              /* moon-672 (thème sombre) */
--terre-battue-975: #FEF4F2;               /* 975 */
--terre-battue-950: #FEE9E5;               /* 950 */
--terre-battue-925: #FDDFD8;               /* 925 */
--terre-battue-850: #FCC0B0;               /* 850 */
```

### 🤎 Famille Marron/Beige

**Marron Café Crème**
```css
--cafe-creme-main: #D1B781;                /* main-782 */
--cafe-creme-sun: #685C48;                 /* sun-383 */
--cafe-creme-moon: #ECD7A2;                /* moon-885 (thème sombre) */
--cafe-creme-975: #FBF6ED;                 /* 975 */
--cafe-creme-950: #F7ECDB;                 /* 950 */
--cafe-creme-925: #F4E3C7;                 /* 925 */
--cafe-creme-850: #E7CA8E;                 /* 850 */
```

**Marron Caramel**
```css
--caramel-main: #C08C65;                   /* main-648 */
--caramel-sun: #845D48;                    /* sun-425 */
--caramel-moon: #FBD8AB;                   /* moon-901 (thème sombre) */
--caramel-975: #FBF5F2;                    /* 975 */
--caramel-950: #F7EBE5;                    /* 950 */
--caramel-925: #F3E2D9;                    /* 925 */
--caramel-850: #EAC7B2;                    /* 850 */
```

**Marron Opéra**
```css
--opera-main: #BD987A;                     /* main-680 */
--opera-sun: #745B47;                      /* sun-395 */
--opera-moon: #E6BE92;                     /* moon-820 (thème sombre) */
--opera-975: #FBF5F2;                      /* 975 */
--opera-950: #F7ECE4;                      /* 950 */
--opera-925: #F3E2D7;                      /* 925 */
--opera-850: #EAC7AD;                      /* 850 */
```

**Beige Gris Galet**
```css
--gris-galet-main: #AEA397;                /* main-702 */
--gris-galet-sun: #6A6156;                 /* sun-407 */
--gris-galet-moon: #D0C3B7;                /* moon-821 (thème sombre) */
--gris-galet-975: #F9F6F2;                 /* 975 */
--gris-galet-950: #F3EDE5;                 /* 950 */
--gris-galet-925: #EEE4D9;                 /* 925 */
--gris-galet-850: #E0CAB0;                 /* 850 */
```

---

## 💻 Utilisation en CSS

### Variables CSS personnalisées
```css
:root {
  /* Couleurs primaires */
  --dsfr-bleu-france: #000091;
  --dsfr-rouge-marianne: #E1000F;
  --dsfr-blanc: #FFFFFF;
  
  /* États interactifs */
  --dsfr-bleu-france-hover: #6196FF;
  --dsfr-bleu-france-active: #85A9FF;
}

/* Exemple d'utilisation */
.button-primary {
  background-color: var(--dsfr-bleu-france);
  color: var(--dsfr-blanc);
}

.button-primary:hover {
  background-color: var(--dsfr-bleu-france-hover);
}

.alert-danger {
  border-color: var(--dsfr-rouge-marianne);
  color: var(--dsfr-rouge-marianne);
}
```

### Classes Tailwind équivalentes
```css
/* À créer dans tailwind.config.js */
colors: {
  'bleu-france': '#000091',
  'rouge-marianne': '#E1000F',
  'bleu-france-hover': '#6196FF',
  'bleu-france-active': '#85A9FF'
}
```

---

## 📋 Guidelines d'usage

### ✅ Recommandations
- **Identité** : Utiliser bleu France pour marquer l'identité de l'État
- **Attention** : Rouge Marianne pour attirer l'attention ou les erreurs
- **Contraste** : Toujours vérifier le ratio 4,5:1 minimum
- **Cohérence** : Respecter la hiérarchie primaire > système > illustrative

### ❌ À éviter
- Modifier les codes couleurs officiels
- Utiliser rouge Marianne en couleur de fond principale
- Créer des dégradés avec les couleurs primaires
- Ignorer les règles de contraste

---

## 🔗 Ressources officielles

- **Site officiel** : [systeme-de-design.gouv.fr](https://www.systeme-de-design.gouv.fr)
- **GitHub** : [GouvernementFR/dsfr](https://github.com/GouvernementFR/dsfr)
- **Palette complète** : [Couleurs DSFR](https://www.systeme-de-design.gouv.fr/version-courante/fr/fondamentaux/couleurs-palette)

---

*Dernière mise à jour : 2025 - Version courante du DSFR*