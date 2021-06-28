# TIL4 부스트코스
df.loc를 사용하면 행,열을 함께 가져올 수 있다.


# folium을 이용해서 지도에 표시
map=folium.Map(location=[df_seoul_hospital['위도'].mean(),df_seoul_hospital['경도'].mean()], zoom_start=12 )
for n in df_seoul_hospital.index:
    name=df_seoul_hospital.loc[n,'상호명']
    address=df_seoul_hospital.loc[n,'도로명주소']
    popup= f"{name}-{address}"
    location = [df_seoul_hospital.loc[n,'위도'],df_seoul_hospital.loc[n,'경도']]
    folium.Marker(
        location= location,
        ppup= popup,
    ).add_to(map)
map

# 데이터 타입 변경 map함수 이용
예시.. 
df['기간'].map(lambda x: int(x.split()[0]))

# legend값을 밖으로 표시
plt.legend(bbox_to_anchor=(1.05,1), loc=2 , borderaxespad=0.)

# 아래값 조절
plt.figure(figsize=(15,4))
plt.xticks(rotation=30)
