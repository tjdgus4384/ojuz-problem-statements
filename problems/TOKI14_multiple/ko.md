좋은 교사는 학생들이 시험을 포함한 다양한 방법을 통해 학습하는 것을 가능하게 합니다. 예를 들어, 교사는 학생들에게 시험 문항들의 정답을 제공함으로서 피드백을 제공할 수 있습니다. 하지만, 어떤 교사들은 이러한 일을 하는 데 별로 관심이 없는 것 같습니다.

승현이는 막 인도네시아어 시험을 보았습니다. 이 시험은 $N$개의 선다형 문제로 구성되어 있습니다. 각 문제의 보기는 `a`, `b`, `c`, `d`, `e`의 5개로 이루어져 있으며, 정답은 반드시 이 보기들 중 하나입니다. 승현이는 이 시험에서 $P$개의 문제를 정확하게 맞혔습니다. 승현이는 각 문제의 정답을 알고 싶어 하지만, 선생님은 절대로 알려주지 않습니다.

승현이는 천재답게 아이디어를 생각해 냅니다. 그는 같은 시험에서 $Q$개의 문제를 맞힌 친구 지학이의 시험 결과를 빌렸습니다. $i$번 문항에서 승현이는 $A_{i}$를, 지학이는 $B_{i}$를 답했습니다. $A_{i}$와 $B_{i}$는 집합 {'a', 'b', 'c', 'd', 'e'}의 원소입니다. 게다가, 승현이는 "반드시 틀릴 수밖에 없는" 보기들을 알고 있습니다. 예를 들어, 1번 문항에서 그는 정답이 'a', 'c', 'd' 중 하나라는 것을 확실히 알고 있고, 2번 문항에서는 정답이 'a' 또는 'e'라는 것을 알고 있으며, ...

승현이는 이 정보들을 가지고 각 문제의 정답을 알아내기를 원합니다. 불운하게도, 이 정보와 일치하는 정답 후보들이 여러 개 있을 수 있습니다. 승현이가 가능한 정답 후보들의 수를 계산할 수 있도록 도와주세요.

### 입력 형식

첫 번째 줄에 세 개의 정수 $N$, $P$와 $Q$가 공백을 사이로 두고 주어집니다. 두 번째 줄에는 승현이가 제시한 답을 나타내는 $N$개의 문자 $A_{1}, A_{2}, \cdots, A_{N}$이 공백을 사이로 두고 주어집니다. 세 번째 줄에는 지학이가 제시한 답을 나타내는 $N$개의 문자 $B_{1}, B_{2}, \cdots, B_{N}$이 공백을 사이로 두고 주어집니다.

다음 $N$개 줄에는 각 문제의 보기들 중 정답이 될 수 있는 것들에 대한 정보가 주어집니다. 각 줄에는 5개의 문자가 주어집니다.

* 첫 번째 문자는 `a` 또는 `.`입니다.
* 두 번째 문자는 `b` 또는 `.`입니다.
* 세 번째 문자는 `c` 또는 `.`입니다.
* 네 번째 문자는 `d` 또는 `.`입니다.
* 다섯 번째 문자는 `e` 또는 `.`입니다.

$i$번째 줄에 {'a', 'b', 'c', 'd', 'e'}에 속한 어떤 문자가 존재한다는 것은 그 보기가 $i$번 문제의 가능한 정답 중 하나라는 것의 필요충분조건입니다. 각 문제 $i$에 대해, $A_{i}$와 $B_{i}$는 이 문제에 해당하는 줄에 나타남이 보장됩니다. 예를 들어, "a.cd."가 주어진다면 이 문제에서 답이 될 수 있는 보기는 'a', 'c', 'd' 중에 하나라는 것입니다.

### 출력 형식

첫 번째 줄에 주어진 정보와 일치하는 정답 후보들의 개수를 1,000,000,007로 나눈 나머지를 출력합니다. 정답 후보가 존재하지 않을 수도 있습니다.

### 예제

<table class='table table-bordered table-condensed'>
 <thead>
  <tr>
   <th style="width: 50%;">입력</th>
   <th style="width: 50%;">출력</th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td class="code-font">5 4 3<br/>
a b c d c<br/>
a b d d c<br/>
a.cd.<br/>
.b...<br/>
..cde<br/>
...d.<br/>
..cd.</td>
   <td class="code-font">3</td>
  </tr>
  <tr>
   <td class="code-font">6 3 3<br/>
a b c d c d<br/>
a b d c d c<br/> 
abc..<br/>
ab...<br/>
..cde<br/>
..cde<br/>
..cde<br/>
..cde</td>
   <td class="code-font">3</td>
  </tr>
 </tbody>
</table>

### 설명

첫 번째 예제에서는 아래와 같은 3개의 정답 후보들이 존재합니다.

* a b c d d
* c b c d c
* d b c d c

두 번째 예제에서, 가능한 정답 후보들은:

* a b c c e e
* a b d d e e
* a b c e d e
* a b d e c e
* ... (a b로 시작하는 정답 후보가 12개 있습니다)
* a a c c c c
* a a c c d d
* a a d d d d
* a a c d d c
* a a d c c d
* b b ... (6개 있습니다)
* c b ... (6개 있습니다)

### 서브태스크

각 서브태스크에서,

* 각 문제 $i$에 대해, $A_{i}$와 $B_{i}$는 입력의 $(3+i)$번째 줄에 존재함이 보장됩니다.

#### 서브태스크 1 (24점)

* $1 \le N \le 200$

#### 서브태스크 2 (16점)

* $1 \le N \le 2,000$
* 각 $i$에 대해 $A_{i} \neq B_{i}$
* 승현이는 각 문제 $i$에 대해 정답이 될 수 있는 보기가 정확히 2개 있다는 것을 알고 있습니다.

#### 서브태스크 1 (60점)

* $1 \le N \le 2,000$