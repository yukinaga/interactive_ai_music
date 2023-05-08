# 目的を指定する

以下は、ChatGPTとやりとりしながら「YouTube用BGM」を作成する例です。  
GPT-4を使用しています。  

## ユーザー:

教育系YouTuberのBGMとして適した曲を、Sonic Piで作ってください。

## ChatGPT:

Sonic Piは、コードで音楽を作成するためのプログラムです。教育系YouTuberのBGMとして適した曲は、リラックスした雰囲気で聞き手の注意をそらさない曲が良いでしょう。以下のSonic Piコードは、そのようなBGMを作成する例です。

```ruby
# Welcome to Sonic Pi
use_bpm 60

live_loop :background do
  with_fx :reverb, mix: 0.5 do
    use_synth :piano
    play_pattern_timed [:c4, :e4, :g4, :c5], [0.5, 0.5, 0.5, 1], amp: 0.5
    play_pattern_timed [:f4, :a4, :c5, :f5], [0.5, 0.5, 0.5, 1], amp: 0.5
    play_pattern_timed [:g4, :b4, :d5, :g5], [0.5, 0.5, 0.5, 1], amp: 0.5
    play_pattern_timed [:c5, :e5, :g5, :c6], [0.5, 0.5, 0.5, 1], amp: 0.5
  end
end

live_loop :beat do
  sample :bd_haus, amp: 0.4
  sleep 1
  sample :drum_cymbal_closed, amp: 0.2
  sleep 1
  sample :bd_haus, amp: 0.4
  sleep 1
  sample :drum_cymbal_closed, amp: 0.2
  sleep 1
end
```

このコードは、穏やかなピアノのメロディとシンプルなビートを組み合わせたBGMを作成します。Sonic Piを起動し、このコードをコピーして貼り付け、実行することでBGMを再生できます。必要に応じて、BPMや楽器、音量などのパラメータを調整して、理想のBGMに仕上げてください。

## ユーザー:

雰囲気は合ってます。飽きずに長く聴けて、ワクワクするような曲にしてください。

## ChatGPT:

ワクワクする雰囲気を追加し、より長く楽しめるようなBGMに変更しました。以下のSonic Piコードを試してみてください。

```ruby
# Welcome to Sonic Pi
use_bpm 90

live_loop :background do
  with_fx :reverb, mix: 0.5 do
    use_synth :piano
    play_pattern_timed [:c4, :e4, :g4, :c5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:f4, :a4, :c5, :f5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:g4, :b4, :d5, :g5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:c5, :e5, :g5, :c6], [0.25, 0.25, 0.25, 0.5], amp: 0.5
  end
end

live_loop :melody do
  with_fx :echo, mix: 0.4, phase: 0.5 do
    use_synth :pluck
    play_pattern_timed [:e4, :r, :g4, :r, :a4, :r, :g4, :r], [0.5], amp: 0.3
  end
  sleep 8
end

live_loop :beat do
  sample :bd_haus, amp: 0.4
  sleep 0.5
  sample :drum_cymbal_closed, amp: 0.2
  sleep 0.5
  sample :bd_haus, amp: 0.4
  sleep 0.5
  sample :drum_cymbal_closed, amp: 0.2
  sleep 0.5
end
```

BPMを90に上げて、より活気のあるリズムにしました。また、ワクワクするメロディを追加し、エコーエフェクトで広がりのあるサウンドを作りました。これで、長時間聴いても飽きない、ワクワクする雰囲気のBGMが作成できます。Sonic Piでコードを実行し、必要に応じて調整してください。

## ユーザー:

いい感じです。ただ、:melody パートが貧弱で単調なので、一旦削除してください。

## ChatGPT:

:melody パートを削除し、シンプルながらもワクワクする雰囲気を維持したBGMを作成しました。以下のSonic Piコードをお試しください。

```ruby
# Welcome to Sonic Pi
use_bpm 90

live_loop :background do
  with_fx :reverb, mix: 0.5 do
    use_synth :piano
    play_pattern_timed [:c4, :e4, :g4, :c5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:f4, :a4, :c5, :f5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:g4, :b4, :d5, :g5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:c5, :e5, :g5, :c6], [0.25, 0.25, 0.25, 0.5], amp: 0.5
  end
end

live_loop :beat do
  sample :bd_haus, amp: 0.4
  sleep 0.5
  sample :drum_cymbal_closed, amp: 0.2
  sleep 0.5
  sample :bd_haus, amp: 0.4
  sleep 0.5
  sample :drum_cymbal_closed, amp: 0.2
  sleep 0.5
end
```

このコードは、穏やかなピアノのメロディとシンプルなビートを組み合わせたBGMを作成します。Sonic Piを起動し、このコードをコピーして貼り付け、実行することでBGMを再生できます。必要に応じて、BPMや楽器、音量などのパラメータを調整して、理想のBGMに仕上げてください。

## ユーザー:

学習意欲が向上する曲にするため、もう一つパートを追加してください。

## ChatGPT:

学習意欲を向上させるために、新しいパートを追加し、刺激的な要素を加えました。以下のSonic Piコードを試してみてください。

```ruby
# Welcome to Sonic Pi
use_bpm 90

live_loop :background do
  with_fx :reverb, mix: 0.5 do
    use_synth :piano
    play_pattern_timed [:c4, :e4, :g4, :c5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:f4, :a4, :c5, :f5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:g4, :b4, :d5, :g5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:c5, :e5, :g5, :c6], [0.25, 0.25, 0.25, 0.5], amp: 0.5
  end
end

live_loop :beat do
  sample :bd_haus, amp: 0.4
  sleep 0.5
  sample :drum_cymbal_closed, amp: 0.2
  sleep 0.5
  sample :bd_haus, amp: 0.4
  sleep 0.5
  sample :drum_cymbal_closed, amp: 0.2
  sleep 0.5
end

live_loop :inspiration do
  with_fx :reverb, mix: 0.4 do
    use_synth :pretty_bell
    play_pattern_timed [:c5, :r, :r, :r, :r, :r, :r, :r], [0.5], amp: 0.3
    sleep 8
  end
end
```

新たに追加した`:inspiration`パートでは、`pretty_bell`シンセサイザを使用して、インスピレーションを感じさせるメロディを作成しました。この新しいパートが学習意欲向上に役立つことを願っています。Sonic Piでコードを実行し、必要に応じて調整してください。

## ユーザー:

:inspiration のパートをもっと面白くしてください。

## ChatGPT:

:inspiration パートをより面白くするために、メロディを少し複雑にしました。以下のSonic Piコードを試してみてください。

```ruby
# Welcome to Sonic Pi
use_bpm 90

live_loop :background do
  with_fx :reverb, mix: 0.5 do
    use_synth :piano
    play_pattern_timed [:c4, :e4, :g4, :c5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:f4, :a4, :c5, :f5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:g4, :b4, :d5, :g5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:c5, :e5, :g5, :c6], [0.25, 0.25, 0.25, 0.5], amp: 0.5
  end
end

live_loop :beat do
  sample :bd_haus, amp: 0.4
  sleep 0.5
  sample :drum_cymbal_closed, amp: 0.2
  sleep 0.5
  sample :bd_haus, amp: 0.4
  sleep 0.5
  sample :drum_cymbal_closed, amp: 0.2
  sleep 0.5
end

live_loop :inspiration do
  with_fx :reverb, mix: 0.4 do
    use_synth :pretty_bell
    play_pattern_timed [:c5, :e5, :g5, :b5, :a5, :g5, :e5, :c5], [0.5], amp: 0.3
    sleep 4
  end
end
```

:inspiration パートでは、`pretty_bell`シンセサイザを使って、より多様な音程のメロディを作成しました。これにより、曲全体がより面白くなります。Sonic Piでコードを実行し、必要に応じて調整してください。

## ユーザー:

曲がさらに良くなりました。同じループの繰り返しになっているので、変化をつけてください。

## ChatGPT:

```
# Welcome to Sonic Pi
use_bpm 90

live_loop :background, auto_cue: false do
  with_fx :reverb, mix: 0.5 do
    use_synth :piano
    play_pattern_timed [:c4, :e4, :g4, :c5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:f4, :a4, :c5, :f5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:g4, :b4, :d5, :g5], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:c5, :e5, :g5, :c6], [0.25, 0.25, 0.25, 0.5], amp: 0.5
    play_pattern_timed [:g5, :d5, :b4, :g4], [0.25, 0.25, 0.25, 0.5], amp: 0.5
  end
end

live_loop :beat, auto_cue: false do
  sample :bd_haus, amp: 0.4
  sleep 0.5
  sample :drum_cymbal_closed, amp: 0.2
  sleep 0.5
  sample :bd_haus, amp: 0.4
  sleep 0.5
  sample :drum_cymbal_closed, amp: 0.2
  sleep 0.5
end

live_loop :inspiration, auto_cue: false do
  with_fx :reverb, mix: 0.4 do
    use_synth :pretty_bell
    play_pattern_timed [:c5, :e5, :g5, :b5, :a5, :g5, :e5, :c5], [0.5], amp: 0.3
    sleep 4
  end
  with_fx :reverb, mix: 0.4 do
    use_synth :pretty_bell
    play_pattern_timed [:g5, :e5, :c5, :a4, :g4, :e4, :c4, :g4], [0.5], amp: 0.3
    sleep 4
  end
end

live_loop :bass, auto_cue: false do
  use_synth :fm
  play_pattern_timed [:c2, :r, :r, :r], [1], amp: 0.3
  sleep 4
  play_pattern_timed [:f2, :r, :r, :r], [1], amp: 0.3
  sleep 4
  play_pattern_timed [:g2, :r, :r, :r], [1], amp: 0.3
  sleep 4
  play_pattern_timed [:c3, :r, :r, :r],
```

## ユーザー:

続き

## ChatGPT:

ごめんなさい、コードが途中で切れてしまいました。以下に、続きのコードを記載します。

```ruby
  sleep 4
  play_pattern_timed [:g2, :r, :r, :r], [1], amp: 0.3
  sleep 4
end
```

このコードでは、以下の変更を加えました。

1. :background パートに、新しいコードを追加し、メロディに変化を付けました。
2. :inspiration パートに、新しいコードを追加し、メロディに変化を付けました。
3. :bass パートを新たに追加し、曲全体に厚みを持たせました。

これらの変更により、曲に変化が生じ、同じループの繰り返しによる単調さが軽減されるでしょう。Sonic Piでコードを実行し、必要に応じて調整してください。
