<template>
    <div class="card">
        <div class="card-left-container">
            <div class="card-image">
                <!-- <img src="http://127.0.0.1/api/images/lot1_room1_1.jpeg" class="imageInCard" alt="фото комнаты"> -->
            <v-img
                src="http://127.0.0.1/api/images/lot2_room1_1.jpeg"
                height="350"
                width="385"
                class="grey darken-4"
            ></v-img>
            </div>
            <div class="card-descr-one">
                <h2>Сдается комната</h2>
                <h3>{{room.address}}</h3>
                <p>
                    <v-icon
                        color="red"
                    >
                        mdi-subway-variant
                    </v-icon>
                    {{room.metro}}
                </p>
                <p>
                    {{room.ttmetro_foot}} минут пешком 
                    &bull;
                    {{room.ttmetro_transport}} минут на транспорте 
                    
                </p>
                <p>
                   Площадь квартиры {{room.flat_area}} м<sup>2</sup>, площадь комнаты {{room.area}} м<sup>2</sup></p>
                <p>Этаж {{room.floor}}/{{room.floor_total}}</p>
                <p class="card-description">
                    {{room.description}}
                </p>
            </div>
        </div>
        <div class="card-descr-two">
            <p>Занято</p>
            <p><span class="n-living-places">{{room.curr_number_of_residents}}/{{room.max_residents}}</span></p>
            <div class="card-descr-two-btns">
                <div class="btn-in-card">
                    <v-btn
                        class="mx-2"
                        fab
                        dark
                        large
                        color="#fff"
                    >
                        <v-icon
                            color="#512DE4"
                        >
                            mdi-eye-off-outline
                        </v-icon>
                    </v-btn>
                </div>
                <div class="btn-in-card">
                    <v-btn
                        class="mx-2"
                        fab
                        dark
                        large
                        color="#fff"

                    >
                        <v-icon
                            color="#512DE4"
                        >
                            mdi-heart-outline
                        </v-icon>
                    </v-btn>
                </div>
            </div>
            <p id="price">{{room.room_price}}&#8381;/месяц</p>
            <div class="default-btn" id="open-lot">
                Подробнее
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        room: {
            type: Object,
        }
    }
}
</script>

<style>
.card{
    margin: 15px 10px;
    min-width: 800px;
    min-height: 380px;
    border: 0px solid #512DE4;
    border-radius: 20px;
    padding: 20px;

    display: flex;
    flex-flow: row wrap;
    justify-content: space-between;

    box-shadow:0px 1px 7px 0px rgba(0,0,0,0.45);
    -webkit-box-shadow:0px 1px 7px 0px rgba(0,0,0,0.45);
    -moz-box-shadow:0px 1px 7px 0px rgba(0,0,0,0.45);
}
.card-left-container{
    display: flex;
    flex-flow: row wrap;
    justify-content: left;

    flex-grow: 2;
}
.card-image{
    position: relative;
    min-width:385px;
    min-height: 350px;
    border-radius: 20px;
    overflow: hidden;
}
.card-descr-one{
    margin: 0px 15px;
    min-width: 200px;
}
.card-descr-one h2{
    max-width: 300px;
    font-size: 30px;
    font-weight: 700;
}
.card-descr-one h3{
    max-width: 300px;
    font-size: 18px;
    font-weight: 700;
    color: #535353;
    margin-bottom: 24px;
}
.v-application p {
    margin-bottom: 5px;
    font-size: 14px;
    font-weight: 400;
    color: #000;
}
.card-descr-two{
    flex-grow: 1;
    text-align: right;
    display: flex;
    flex-flow: column wrap;
    align-items: flex-end;
}
.n-living-places{
    font-weight: 700;
    color:#512DE4;
    font-size: 38px;
}
#price{
    font-weight: 700;
    font-size: 30px;
    color: #000;
}
.card-descr-two-btns{
    display: flex;
    flex-flow: column wrap;
    justify-content: space-between;
    align-content:flex-end;
}
.btn-in-card{
    margin: 5px 0px;
}
#open-lot{
    padding: 12px 0px;
    text-align: center;
}
.card-description{
    max-width: 400px;
}
</style>