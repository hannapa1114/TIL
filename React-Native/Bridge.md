### StyleSheet, Text, View

```
<View>
  <Text>Hello, world</Text>
</View>
```
- View : div와 비슷한 역할을 하는 태그
- Text : span과 비슷한 역할을 하는 태그

```
const styles = StyleSheet.create({
  container: {
      flex: 1,
      backgroundColor: '#fff'
      fontSize: '10px',
      alignItems: 'center'
  }
})
```
- css는 선택자 객체를 만들어서 적용한다.(css네이밍은 카멜케이스로)

```
<View style={styles.container}>
  <Text>Hello, world</Text>
</View>
```
