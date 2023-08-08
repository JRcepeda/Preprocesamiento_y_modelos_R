{
  "cells": [
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "I5Jua_lUuH8n",
        "outputId": "d9dc8a0b-4aa3-4e7e-d83f-474984ad077c"
      },
      "outputs": [
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "Installing package into ‘/usr/local/lib/R/site-library’\n",
            "(as ‘lib’ is unspecified)\n",
            "\n"
          ]
        }
      ],
      "source": [
        "install.packages('randomForest')"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "2_EvLB_UzDdz",
        "outputId": "d67e6f01-4c64-4fca-ce83-47ad2092c614"
      },
      "outputs": [
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "Installing package into ‘/usr/local/lib/R/site-library’\n",
            "(as ‘lib’ is unspecified)\n",
            "\n"
          ]
        }
      ],
      "source": [
        "install.packages('caret')"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "install.packages('Metrics')"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "3Ggcqz4JPeyp",
        "outputId": "5edacfca-9817-4213-fec9-906cb38f5638"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "Installing package into ‘/usr/local/lib/R/site-library’\n",
            "(as ‘lib’ is unspecified)\n",
            "\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "library(Metrics)"
      ],
      "metadata": {
        "id": "gr6PPeJsPiDU"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "0YGy3BTnzHW3"
      },
      "outputs": [],
      "source": [
        "library(caret)"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "So629FFAuSlT"
      },
      "outputs": [],
      "source": [
        "require(randomForest)"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "k0WEH7cKucdY"
      },
      "outputs": [],
      "source": [
        "datos<-read.csv(\"/content/datos_s (1).csv\")"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 34
        },
        "id": "CoyJS6CfwX7w",
        "outputId": "e24c52ac-938c-4aa8-b177-9fd9d6241f2e"
      },
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "text/html": [
              "<style>\n",
              ".list-inline {list-style: none; margin:0; padding: 0}\n",
              ".list-inline>li {display: inline-block}\n",
              ".list-inline>li:not(:last-child)::after {content: \"\\00b7\"; padding: 0 .5ex}\n",
              "</style>\n",
              "<ol class=list-inline><li>2261</li><li>14</li></ol>\n"
            ],
            "text/markdown": "1. 2261\n2. 14\n\n\n",
            "text/latex": "\\begin{enumerate*}\n\\item 2261\n\\item 14\n\\end{enumerate*}\n",
            "text/plain": [
              "[1] 2261   14"
            ]
          },
          "metadata": {}
        }
      ],
      "source": [
        "dim(datos)"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 445
        },
        "id": "sF-RyjJTu7Bv",
        "outputId": "0d758106-fd59-49d0-da9b-b19a223a59f6"
      },
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "text/html": [
              "<table class=\"dataframe\">\n",
              "<caption>A data.frame: 6 × 14</caption>\n",
              "<thead>\n",
              "\t<tr><th></th><th scope=col>title</th><th scope=col>artist</th><th scope=col>top.genre</th><th scope=col>year</th><th scope=col>bpm</th><th scope=col>energy</th><th scope=col>danceability</th><th scope=col>dB</th><th scope=col>liveness</th><th scope=col>valence</th><th scope=col>duration</th><th scope=col>acousticness</th><th scope=col>speechiness</th><th scope=col>popularity</th></tr>\n",
              "\t<tr><th></th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th></tr>\n",
              "</thead>\n",
              "<tbody>\n",
              "\t<tr><th scope=row>1</th><td>Flowers                               </td><td>0</td><td>0</td><td>2023</td><td>118</td><td>68</td><td>71</td><td>-4</td><td> 3</td><td>65</td><td>200</td><td> 6</td><td> 7</td><td>98</td></tr>\n",
              "\t<tr><th scope=row>2</th><td>Cupid - Twin Ver.                     </td><td>1</td><td>1</td><td>2023</td><td>120</td><td>59</td><td>78</td><td>-8</td><td>35</td><td>73</td><td>174</td><td>44</td><td> 3</td><td>97</td></tr>\n",
              "\t<tr><th scope=row>3</th><td>BESO                                  </td><td>2</td><td>0</td><td>2023</td><td> 95</td><td>64</td><td>77</td><td>-7</td><td>17</td><td>53</td><td>195</td><td>74</td><td>14</td><td>96</td></tr>\n",
              "\t<tr><th scope=row>4</th><td>Boy's a liar Pt. 2                    </td><td>3</td><td>2</td><td>2023</td><td>133</td><td>81</td><td>70</td><td>-8</td><td>25</td><td>86</td><td>131</td><td>25</td><td> 5</td><td>96</td></tr>\n",
              "\t<tr><th scope=row>5</th><td>Creepin' (with The Weeknd &amp; 21 Savage)</td><td>4</td><td>3</td><td>2022</td><td> 98</td><td>62</td><td>72</td><td>-6</td><td> 8</td><td>17</td><td>222</td><td>42</td><td> 5</td><td>96</td></tr>\n",
              "\t<tr><th scope=row>6</th><td>Daylight                              </td><td>5</td><td>4</td><td>2023</td><td>130</td><td>43</td><td>51</td><td>-9</td><td> 9</td><td>32</td><td>213</td><td>83</td><td> 3</td><td>96</td></tr>\n",
              "</tbody>\n",
              "</table>\n"
            ],
            "text/markdown": "\nA data.frame: 6 × 14\n\n| <!--/--> | title &lt;chr&gt; | artist &lt;int&gt; | top.genre &lt;int&gt; | year &lt;int&gt; | bpm &lt;int&gt; | energy &lt;int&gt; | danceability &lt;int&gt; | dB &lt;int&gt; | liveness &lt;int&gt; | valence &lt;int&gt; | duration &lt;int&gt; | acousticness &lt;int&gt; | speechiness &lt;int&gt; | popularity &lt;int&gt; |\n|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|\n| 1 | Flowers                                | 0 | 0 | 2023 | 118 | 68 | 71 | -4 |  3 | 65 | 200 |  6 |  7 | 98 |\n| 2 | Cupid - Twin Ver.                      | 1 | 1 | 2023 | 120 | 59 | 78 | -8 | 35 | 73 | 174 | 44 |  3 | 97 |\n| 3 | BESO                                   | 2 | 0 | 2023 |  95 | 64 | 77 | -7 | 17 | 53 | 195 | 74 | 14 | 96 |\n| 4 | Boy's a liar Pt. 2                     | 3 | 2 | 2023 | 133 | 81 | 70 | -8 | 25 | 86 | 131 | 25 |  5 | 96 |\n| 5 | Creepin' (with The Weeknd &amp; 21 Savage) | 4 | 3 | 2022 |  98 | 62 | 72 | -6 |  8 | 17 | 222 | 42 |  5 | 96 |\n| 6 | Daylight                               | 5 | 4 | 2023 | 130 | 43 | 51 | -9 |  9 | 32 | 213 | 83 |  3 | 96 |\n\n",
            "text/latex": "A data.frame: 6 × 14\n\\begin{tabular}{r|llllllllllllll}\n  & title & artist & top.genre & year & bpm & energy & danceability & dB & liveness & valence & duration & acousticness & speechiness & popularity\\\\\n  & <chr> & <int> & <int> & <int> & <int> & <int> & <int> & <int> & <int> & <int> & <int> & <int> & <int> & <int>\\\\\n\\hline\n\t1 & Flowers                                & 0 & 0 & 2023 & 118 & 68 & 71 & -4 &  3 & 65 & 200 &  6 &  7 & 98\\\\\n\t2 & Cupid - Twin Ver.                      & 1 & 1 & 2023 & 120 & 59 & 78 & -8 & 35 & 73 & 174 & 44 &  3 & 97\\\\\n\t3 & BESO                                   & 2 & 0 & 2023 &  95 & 64 & 77 & -7 & 17 & 53 & 195 & 74 & 14 & 96\\\\\n\t4 & Boy's a liar Pt. 2                     & 3 & 2 & 2023 & 133 & 81 & 70 & -8 & 25 & 86 & 131 & 25 &  5 & 96\\\\\n\t5 & Creepin' (with The Weeknd \\& 21 Savage) & 4 & 3 & 2022 &  98 & 62 & 72 & -6 &  8 & 17 & 222 & 42 &  5 & 96\\\\\n\t6 & Daylight                               & 5 & 4 & 2023 & 130 & 43 & 51 & -9 &  9 & 32 & 213 & 83 &  3 & 96\\\\\n\\end{tabular}\n",
            "text/plain": [
              "  title                                  artist top.genre year bpm energy\n",
              "1 Flowers                                0      0         2023 118 68    \n",
              "2 Cupid - Twin Ver.                      1      1         2023 120 59    \n",
              "3 BESO                                   2      0         2023  95 64    \n",
              "4 Boy's a liar Pt. 2                     3      2         2023 133 81    \n",
              "5 Creepin' (with The Weeknd & 21 Savage) 4      3         2022  98 62    \n",
              "6 Daylight                               5      4         2023 130 43    \n",
              "  danceability dB liveness valence duration acousticness speechiness popularity\n",
              "1 71           -4  3       65      200       6            7          98        \n",
              "2 78           -8 35       73      174      44            3          97        \n",
              "3 77           -7 17       53      195      74           14          96        \n",
              "4 70           -8 25       86      131      25            5          96        \n",
              "5 72           -6  8       17      222      42            5          96        \n",
              "6 51           -9  9       32      213      83            3          96        "
            ]
          },
          "metadata": {}
        }
      ],
      "source": [
        "head(datos)"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 34
        },
        "id": "2VpvcGmYu8YU",
        "outputId": "f0e68b7c-32e3-4df4-c768-d5069a5c06f0"
      },
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "text/html": [
              "0"
            ],
            "text/markdown": "0",
            "text/latex": "0",
            "text/plain": [
              "[1] 0"
            ]
          },
          "metadata": {}
        }
      ],
      "source": [
        "anyDuplicated(datos$title)"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "g4j56TmMv-PF"
      },
      "outputs": [],
      "source": [
        "datos=datos[!duplicated(datos$title),]"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 34
        },
        "id": "TVs5nMgtwIXp",
        "outputId": "bbae87a2-8955-434b-fa0a-7812569d2f67"
      },
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "text/html": [
              "<style>\n",
              ".list-inline {list-style: none; margin:0; padding: 0}\n",
              ".list-inline>li {display: inline-block}\n",
              ".list-inline>li:not(:last-child)::after {content: \"\\00b7\"; padding: 0 .5ex}\n",
              "</style>\n",
              "<ol class=list-inline><li>2261</li><li>13</li></ol>\n"
            ],
            "text/markdown": "1. 2261\n2. 13\n\n\n",
            "text/latex": "\\begin{enumerate*}\n\\item 2261\n\\item 13\n\\end{enumerate*}\n",
            "text/plain": [
              "[1] 2261   13"
            ]
          },
          "metadata": {}
        }
      ],
      "source": [
        "dim(datos)"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "i-MS7qhyyXwm"
      },
      "outputs": [],
      "source": [
        "titulo=datos$title"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "ogC0ZqyKzbiH"
      },
      "outputs": [],
      "source": [
        "rownames(datos)=datos$title"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "V9qP2abMxVk3"
      },
      "outputs": [],
      "source": [
        "datos=datos[,-which(names(datos)=='title')]"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "c-a4FR3kx76b",
        "outputId": "44c9fa3f-f6c7-43fa-b84d-575b42d863fd"
      },
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "      artist    top.genre         year          bpm       energy danceability \n",
            "   \"integer\"    \"integer\"    \"integer\"    \"integer\"    \"integer\"    \"integer\" \n",
            "          dB     liveness      valence     duration acousticness  speechiness \n",
            "   \"integer\"    \"integer\"    \"integer\"    \"integer\"    \"integer\"    \"integer\" \n",
            "  popularity \n",
            "   \"integer\" \n"
          ]
        }
      ],
      "source": [
        "print(sapply(datos,class))"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "Ya5MWqimyfU7"
      },
      "outputs": [],
      "source": [
        "#datos$artist=as.integer(as.factor(datos$artist))-1"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "#datos$top.genre=as.integer(as.factor(datos$top.genre))-1"
      ],
      "metadata": {
        "id": "6R2vWIPwmnpv"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "hBSeakqX0-wO"
      },
      "outputs": [],
      "source": [
        "set.seed(12)\n",
        "traini=createDataPartition(datos$popularity,p=0.8,list=FALSE)"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "bEdWdmcR1kXE"
      },
      "outputs": [],
      "source": [
        "test=datos[-traini,]"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "iGwQHwVz16FK"
      },
      "outputs": [],
      "source": [
        "train=datos[traini,]"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "sum(is.na(datos))"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 34
        },
        "id": "FobAh7TOceu8",
        "outputId": "abeb09c3-4818-4e6e-cd66-4f7a39ad9957"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "text/html": [
              "0"
            ],
            "text/markdown": "0",
            "text/latex": "0",
            "text/plain": [
              "[1] 0"
            ]
          },
          "metadata": {}
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "print(sapply(datos,class))"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "jfkoZxsgh9cL",
        "outputId": "d9826903-e109-47fa-be11-7a314cf104e2"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "      artist    top.genre         year          bpm       energy danceability \n",
            "   \"integer\"    \"integer\"    \"integer\"    \"integer\"    \"integer\"    \"integer\" \n",
            "          dB     liveness      valence     duration acousticness  speechiness \n",
            "   \"integer\"    \"integer\"    \"integer\"    \"integer\"    \"integer\"    \"integer\" \n",
            "  popularity \n",
            "   \"integer\" \n"
          ]
        }
      ]
    },
    {
      "cell_type": "markdown",
      "source": [
        "#Bosque aleatorio 1:\n",
        "\n",
        "Estimadores 250 y profundidad 50"
      ],
      "metadata": {
        "id": "JFoPmn_cXbi9"
      }
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "o7uYo4a62PJY"
      },
      "outputs": [],
      "source": [
        "bosque1=randomForest(popularity~.,data=train,ntree=250,nodesize=2,splitrule=\"mse\",maxdepth=50,importance = TRUE)"
      ]
    },
    {
      "cell_type": "code",
      "execution_count": null,
      "metadata": {
        "id": "henww-UD3esi"
      },
      "outputs": [],
      "source": [
        "PredB1=predict(bosque1,test)"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "r2_score<-function(test,pred){\n",
        "  meanYt=mean(test$popularity)\n",
        "  N=sum(((test$popularity-pred)**2))\n",
        "  D=sum(((test$popularity-meanYt)**2))\n",
        "  r2=1-(N/D)\n",
        "  return (r2)\n",
        "}"
      ],
      "metadata": {
        "id": "-uQVyourQVRK"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "MetricB1=r2_score(test,PredB1)"
      ],
      "metadata": {
        "id": "sGv6RWQ9RDuJ"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "source": [
        "#Bosque aleatorio 2:\n",
        "\n",
        "Estimadores 250 y profundidad 150"
      ],
      "metadata": {
        "id": "T_xObNZVX0PN"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "bosque2=randomForest(popularity~.,ntree=250,maxdepth=150,splitrule='mse',data=train)"
      ],
      "metadata": {
        "id": "Po5_6iGkWPcp"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "PredB2=predict(bosque2,test)"
      ],
      "metadata": {
        "id": "RuHvKXKmYRVm"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "MetricB2=r2_score(test,PredB2)"
      ],
      "metadata": {
        "id": "jDJVpxh2YXOU"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "source": [
        "#Bosque aleatorio 3:\n",
        "\n",
        "Estimadores 500 y profundidad 50"
      ],
      "metadata": {
        "id": "yYi3KmKmaBOY"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "bosque3=randomForest(popularity~.,ntree=500,maxdepth=50,splitrule='mse',data=train)"
      ],
      "metadata": {
        "id": "XoXVSCZIYrAY"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "PredB3=predict(bosque3,test)"
      ],
      "metadata": {
        "id": "SbSH9yblaKyw"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "MetricB3=r2_score(test,PredB3)"
      ],
      "metadata": {
        "id": "ky44ySPSaNXb"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "source": [
        "#Bosque aleatorio 4:\n",
        "\n",
        "Estimadores 500 y profundidad 150"
      ],
      "metadata": {
        "id": "hgYLgUk1alkk"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "bosque4=randomForest(popularity~.,ntree=500,maxdepth=150,splitrule='mse',data=train)"
      ],
      "metadata": {
        "id": "alBYBdCzaUE3"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "PredB4=predict(bosque4,test)"
      ],
      "metadata": {
        "id": "uvlcaYZ-aron"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "MetricB4=r2_score(test,PredB4)"
      ],
      "metadata": {
        "id": "Rn_KHVmlay43"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "markdown",
      "source": [
        "#Resultados"
      ],
      "metadata": {
        "id": "a0XPLv19b6Jl"
      }
    },
    {
      "cell_type": "code",
      "source": [
        "Modelo=c('Bosque 1  Estimadores 250 Profundidad 50','Bosque 2  Estimadores 250 Profundidad 150','Bosque 3  Estimadores 500 Profundidad 50','Bosque 4  Estimadores 500 Profundidad 150')"
      ],
      "metadata": {
        "id": "zeBj1Ojea7yv"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "R2=c(MetricB1,MetricB2,MetricB3,MetricB4)"
      ],
      "metadata": {
        "id": "HJhaziEVbXCS"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "resultados=data.frame(Modelo,R2)"
      ],
      "metadata": {
        "id": "SYX9ZVSfbgFR"
      },
      "execution_count": null,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "resultados"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 224
        },
        "id": "WcjzeLbFbiCf",
        "outputId": "cc0e3ba6-786e-4c2f-97ec-c138ba70c6fc"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "text/html": [
              "<table class=\"dataframe\">\n",
              "<caption>A data.frame: 4 × 2</caption>\n",
              "<thead>\n",
              "\t<tr><th scope=col>Modelo</th><th scope=col>R2</th></tr>\n",
              "\t<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;dbl&gt;</th></tr>\n",
              "</thead>\n",
              "<tbody>\n",
              "\t<tr><td>Bosque 1  Estimadores 250 Profundidad 50 </td><td>0.6818921</td></tr>\n",
              "\t<tr><td>Bosque 2  Estimadores 250 Profundidad 150</td><td>0.6740856</td></tr>\n",
              "\t<tr><td>Bosque 3  Estimadores 500 Profundidad 50 </td><td>0.6797404</td></tr>\n",
              "\t<tr><td>Bosque 4  Estimadores 500 Profundidad 150</td><td>0.6818140</td></tr>\n",
              "</tbody>\n",
              "</table>\n"
            ],
            "text/markdown": "\nA data.frame: 4 × 2\n\n| Modelo &lt;chr&gt; | R2 &lt;dbl&gt; |\n|---|---|\n| Bosque 1  Estimadores 250 Profundidad 50  | 0.6818921 |\n| Bosque 2  Estimadores 250 Profundidad 150 | 0.6740856 |\n| Bosque 3  Estimadores 500 Profundidad 50  | 0.6797404 |\n| Bosque 4  Estimadores 500 Profundidad 150 | 0.6818140 |\n\n",
            "text/latex": "A data.frame: 4 × 2\n\\begin{tabular}{ll}\n Modelo & R2\\\\\n <chr> & <dbl>\\\\\n\\hline\n\t Bosque 1  Estimadores 250 Profundidad 50  & 0.6818921\\\\\n\t Bosque 2  Estimadores 250 Profundidad 150 & 0.6740856\\\\\n\t Bosque 3  Estimadores 500 Profundidad 50  & 0.6797404\\\\\n\t Bosque 4  Estimadores 500 Profundidad 150 & 0.6818140\\\\\n\\end{tabular}\n",
            "text/plain": [
              "  Modelo                                    R2       \n",
              "1 Bosque 1  Estimadores 250 Profundidad 50  0.6818921\n",
              "2 Bosque 2  Estimadores 250 Profundidad 150 0.6740856\n",
              "3 Bosque 3  Estimadores 500 Profundidad 50  0.6797404\n",
              "4 Bosque 4  Estimadores 500 Profundidad 150 0.6818140"
            ]
          },
          "metadata": {}
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "bosque1$importance"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 443
        },
        "id": "ZzA1qW7rsniM",
        "outputId": "45489cad-3e5d-413a-84d7-dfb4c2b67623"
      },
      "execution_count": null,
      "outputs": [
        {
          "output_type": "display_data",
          "data": {
            "text/html": [
              "<table class=\"dataframe\">\n",
              "<caption>A matrix: 12 × 2 of type dbl</caption>\n",
              "<thead>\n",
              "\t<tr><th></th><th scope=col>%IncMSE</th><th scope=col>IncNodePurity</th></tr>\n",
              "</thead>\n",
              "<tbody>\n",
              "\t<tr><th scope=row>artist</th><td>119.8549199</td><td>105287.737</td></tr>\n",
              "\t<tr><th scope=row>top.genre</th><td> 11.4080467</td><td> 22222.320</td></tr>\n",
              "\t<tr><th scope=row>year</th><td> 18.7810601</td><td> 24301.765</td></tr>\n",
              "\t<tr><th scope=row>bpm</th><td>  0.1739223</td><td>  9559.111</td></tr>\n",
              "\t<tr><th scope=row>energy</th><td>  4.2770938</td><td>  8846.653</td></tr>\n",
              "\t<tr><th scope=row>danceability</th><td>  1.3955506</td><td>  9054.562</td></tr>\n",
              "\t<tr><th scope=row>dB</th><td>  1.3866674</td><td>  5022.627</td></tr>\n",
              "\t<tr><th scope=row>liveness</th><td>  0.3755932</td><td>  7917.464</td></tr>\n",
              "\t<tr><th scope=row>valence</th><td>  0.8030673</td><td>  8781.180</td></tr>\n",
              "\t<tr><th scope=row>duration</th><td>  1.6701826</td><td> 11057.720</td></tr>\n",
              "\t<tr><th scope=row>acousticness</th><td>  0.7840511</td><td>  7637.180</td></tr>\n",
              "\t<tr><th scope=row>speechiness</th><td>  0.5926807</td><td>  6743.586</td></tr>\n",
              "</tbody>\n",
              "</table>\n"
            ],
            "text/markdown": "\nA matrix: 12 × 2 of type dbl\n\n| <!--/--> | %IncMSE | IncNodePurity |\n|---|---|---|\n| artist | 119.8549199 | 105287.737 |\n| top.genre |  11.4080467 |  22222.320 |\n| year |  18.7810601 |  24301.765 |\n| bpm |   0.1739223 |   9559.111 |\n| energy |   4.2770938 |   8846.653 |\n| danceability |   1.3955506 |   9054.562 |\n| dB |   1.3866674 |   5022.627 |\n| liveness |   0.3755932 |   7917.464 |\n| valence |   0.8030673 |   8781.180 |\n| duration |   1.6701826 |  11057.720 |\n| acousticness |   0.7840511 |   7637.180 |\n| speechiness |   0.5926807 |   6743.586 |\n\n",
            "text/latex": "A matrix: 12 × 2 of type dbl\n\\begin{tabular}{r|ll}\n  & \\%IncMSE & IncNodePurity\\\\\n\\hline\n\tartist & 119.8549199 & 105287.737\\\\\n\ttop.genre &  11.4080467 &  22222.320\\\\\n\tyear &  18.7810601 &  24301.765\\\\\n\tbpm &   0.1739223 &   9559.111\\\\\n\tenergy &   4.2770938 &   8846.653\\\\\n\tdanceability &   1.3955506 &   9054.562\\\\\n\tdB &   1.3866674 &   5022.627\\\\\n\tliveness &   0.3755932 &   7917.464\\\\\n\tvalence &   0.8030673 &   8781.180\\\\\n\tduration &   1.6701826 &  11057.720\\\\\n\tacousticness &   0.7840511 &   7637.180\\\\\n\tspeechiness &   0.5926807 &   6743.586\\\\\n\\end{tabular}\n",
            "text/plain": [
              "             %IncMSE     IncNodePurity\n",
              "artist       119.8549199 105287.737   \n",
              "top.genre     11.4080467  22222.320   \n",
              "year          18.7810601  24301.765   \n",
              "bpm            0.1739223   9559.111   \n",
              "energy         4.2770938   8846.653   \n",
              "danceability   1.3955506   9054.562   \n",
              "dB             1.3866674   5022.627   \n",
              "liveness       0.3755932   7917.464   \n",
              "valence        0.8030673   8781.180   \n",
              "duration       1.6701826  11057.720   \n",
              "acousticness   0.7840511   7637.180   \n",
              "speechiness    0.5926807   6743.586   "
            ]
          },
          "metadata": {}
        }
      ]
    }
  ],
  "metadata": {
    "colab": {
      "provenance": [],
      "authorship_tag": "ABX9TyPHu+ThIt09FbAkMaqcc/Dc"
    },
    "kernelspec": {
      "display_name": "R",
      "name": "ir"
    },
    "language_info": {
      "name": "R"
    }
  },
  "nbformat": 4,
  "nbformat_minor": 0
}
