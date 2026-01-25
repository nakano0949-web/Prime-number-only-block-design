# Prime-number-only-block-design
<script  language="javascript" type="text/javascript">

//素数p 300以下一覧

//3	5	7	11

//13	17	19	23	29

//31	37	41	43	47

//53	59	61	67	71

//73	79	83	89	97

//101	103	107	109	113

//127	131	137	139	149

//151	157	163	167	173

//179	181	191	193	197

//199	211	223	227	229

//233	239	241	251	257

//263	269	271	277	281

//283	293	                                 

const p = 173

const q = p**2+p+1



const array=[ ]

for (let num = 0; num < q; num++) { 

 array.push(num); 

}



 

const array1=[]

for(let i=1;i<=p;i++){

array1[i-1]=array.filter((value)=>{

if(p*(i+1) >= value && p*i < value){

return value;

 }

 });

};

 

 

const array0=[];

const afine=[ ];

for (let num = 1; num < q; num+=p) { 

const u = function(u){

return array[num+u]

}

const l = function(u){

return array[num+u]-p-1

}

const datan = [0];

const dataa = [];

for(let h = 0; h < p; h++) {

datan[h+1]=u(h);

dataa[h]=l(h);

}//↓射影平面

 array0.push(datan); //0とu(p-1)までを格納する

 //↓アフィン平面

 afine.push(dataa); //l(p-1)までを格納する

}



for(let i = 0; i < p; i++){

for (let num = 0; num < p; num++) { 



const n = function(n){                    //射影平面のアフィン平面部分に使用する関数

 return array1[n][(num+i*n)%array1[n].length]

 };

 

 const a = function(n){                   //アフィン平面に使用する関数

 return array1[n][(num+i*n)%array1[n].length]-p-1

 };

 

  const ndata = [array[i+1]];

  const adata = [];

for(let h = 0; h < p; h++) {

  //↓射影平面

ndata[h+1]=n(h);

//↓アフィン平面

adata[h]=a(h);

}

array0.push(ndata);                      //[array[i+1]とn(p-1)までを格納する

afine.push(adata);                       //a(p-1)までを格納する 

afine[0]='';

}};

console.log(array0);

console.log(afine);

</script>
