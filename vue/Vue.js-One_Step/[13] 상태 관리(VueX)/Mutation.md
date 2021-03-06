# Mutation 변이

<strong>복습!</strong>
- 저장소 객체 : store
- 저장소 객체에 있는 상태 값 : state


- Mutation는 저장소 객체(store) 안에서 객체에 있는 상태 값(state)을 변경하는데 사용되는 메서드입니다.
변이 메서드를 사용하는 건 저장소 객체의 상태 값은 변이 메서드로만 변경할 수 있기 때문입니다.

```
    const store  = new Vuex.Store({
        state: {
            count: 1
        },
        mutations:{
            increment(state){
                //상태변이
                state.count++;
            }
        }
    });
```
<em>예시 코드</em>

 변이 메서드의 호출은 저장소 객체(store)의 commit 메서드를 사용합니다. 
 
 위의 예시코드 변의 메서드를 호출할때의 코드
 ```
    store.commit("increment");
 ```
 변이 메서드는 추가 인자를 받을 수 있습니다.
 추가 인자를 '페이로드'라고 부름니다.

다음은 페이로드를 전달받는 변이 메서드를 사용하는 예시 코드입니다!
 ```
    const store = new Vuex.Store({
        state:{
            count: 1
        },
        mutations:{
            increment(state,payload){
                state.count += payload.amount
            }
        }
    })
 ```


변이 메서드는 첫 번째 인자로 반드시 state인자를 전달받습니다. state인자는 저장소 객체의 state객체 입니다. 두 번째 인자로 페이로드 값을 명시하면 됩니다.

위의 예시코드에서 increment에 페이로드 인자를 전달하여 실행하는 코드입니다.
```
    store.commit('increment',{
        amount: 10
    }) 
    // 이렇게도 전달할 수 있습니다!
   store.commit({
        type: 'increment',
        amount: 10
    }) 
```

상수를 변이 메서드 이름으로 사용할 수 있습니다.
사용하려면 변이 메서드를 선언할 때 상수 이름을 대괄호로 감싸야 합니다. <br />
그리고, 가능하다며 상수 이름을 별도의 파일로 독립시키는 것이 좋습니다.


변이 메서드의 이름을 상수로 입력했을때의 예시 코드입니다.

```
    const SOME_MUTATION = 'SOME_MUTATION';

    var store = new Vuex.Store({
        state: {
            lucky: 0
        },
        mutations: {
            [SOME_MUTATION](state){
                console.log(state.lucky);
            }
        }
    });
```

```
    var store = new Vuex.Store({
        state:{
            lucky: 0
        },
        mutations:{
            sync_mutation(state){
                console.log(state.lucky);
            }
        }
    });

    var vm = new Vue({
        store: 'store',
        methods:{
            ...Vuex.mapMutations(['sync_mutation'])
        }
    });
```


