# ジャンルを指定する

以下は、ChatGPTとやりとりしながら「アンビエントな曲」を作る例です。  
GPT-4を使用しています。  

## ユーザー:

リラックスできるアンビエントな曲を、Sonic Piで作ってください。

## ChatGPT:

Sonic Piは、音楽をコーディングするためのプログラミング言語です。リラックスできるアンビエントな曲を作るために、以下のサンプルコードを使用してください。

```ruby
use_bpm 60

live_loop :ambient_pad do
  with_fx :reverb, mix: 0.7, room: 0.8 do
    with_fx :slicer, phase: 2, wave: 1, mix: 0.3 do
      use_synth :dsaw
      use_synth_defaults attack: 4, release: 8, amp: 0.4, cutoff: 70
      play_chord chord(:D3, :m9), pan: 0.5
      sleep 8
      play_chord chord(:E3, :m9), pan: -0.5
      sleep 8
    end
  end
end

live_loop :bells do
  with_fx :echo, mix: 0.5, decay: 6 do
    use_synth :fm
    use_synth_defaults attack: 0.5, release: 3, amp: 0.3
    play scale(:D5, :minor_pentatonic, num_octaves: 1).choose
    sleep [0.5, 1, 1.5].choose
  end
end
```

このコードは、Sonic Piに貼り付けて実行することができます。アンビエントパッドの音色と、エコーをかけたベルの音色が組み合わさって、リラックスできるアンビエントな曲が演奏されます。

自分の好みに合わせて、`use_bpm`でテンポを変更したり、`play_chord`や`play`で演奏されるコードや音階を変更したり、`with_fx`でエフェクトを調整したりしてみてください。

## ユーザー:

もう一つパートを加えてください。

## ChatGPT:

もちろん、もう一つのパートを追加して、曲にさらなる深みを加えましょう。以下のコードを先ほどのコードに追加して、新たなパートを組み込んでください。

```ruby
live_loop :background_arp do
  with_fx :reverb, mix: 0.4, room: 0.7 do
    with_fx :slicer, phase: 1, wave: 0, mix: 0.2 do
      use_synth :pluck
      use_synth_defaults attack: 0.1, release: 1, amp: 0.2
      play_pattern_timed (scale :D4, :minor7, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      sleep 4
    end
  end
end
```

この追加されたパートでは、リバーブとスライサーエフェクトを使用して、アルペジオ風のパターンを演奏しています。このパートは、先ほどのアンビエントパッドとベルのパートに合わせて、曲に複雑さとリズム感を加える効果があります。これで、3つのパートが組み合わさったリラックスできるアンビエントな曲が完成しました。

追加のパートも、音色やエフェクト、演奏される音階などをカスタマイズして、自分の好みに合わせて調整してみてください。

## ユーザー:

エラーが発生するので修正してください。

## ChatGPT:

すみません、そのエラーは私のミスです。`live_loop`の同期が抜けていました。以下の修正済みコードをお試しください。

```ruby
use_bpm 60

live_loop :ambient_pad do
  with_fx :reverb, mix: 0.7, room: 0.8 do
    with_fx :slicer, phase: 2, wave: 1, mix: 0.3 do
      use_synth :dsaw
      use_synth_defaults attack: 4, release: 8, amp: 0.4, cutoff: 70
      play_chord chord(:D3, :m9), pan: 0.5
      sleep 8
      play_chord chord(:E3, :m9), pan: -0.5
      sleep 8
    end
  end
end

live_loop :bells do
  sync :ambient_pad
  with_fx :echo, mix: 0.5, decay: 6 do
    use_synth :fm
    use_synth_defaults attack: 0.5, release: 3, amp: 0.3
    play scale(:D5, :minor_pentatonic, num_octaves: 1).choose
    sleep [0.5, 1, 1.5].choose
  end
end

live_loop :background_arp do
  sync :ambient_pad
  with_fx :reverb, mix: 0.4, room: 0.7 do
    with_fx :slicer, phase: 1, wave: 0, mix: 0.2 do
      use_synth :pluck
      use_synth_defaults attack: 0.1, release: 1, amp: 0.2
      play_pattern_timed (scale :D4, :minor7, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      sleep 4
    end
  end
end
```

この修正済みコードでは、`:bells`と`:background_arp`の`live_loop`が`:ambient_pad`の`live_loop`と同期するようになっています。これで、エラーが発生しないで実行できるはずです。コードをSonic Piに貼り付けて、リラックスできるアンビエントな曲をお楽しみください。

## ユーザー:

Unknown scale name: :minor7というエラーが表示されます。修正してください。

## ChatGPT:

すみません、スケールの名前が間違っていました。`:minor7`ではなく、`:dorian`を使用して、修正したコードをお試しください。

```ruby
use_bpm 60

live_loop :ambient_pad do
  with_fx :reverb, mix: 0.7, room: 0.8 do
    with_fx :slicer, phase: 2, wave: 1, mix: 0.3 do
      use_synth :dsaw
      use_synth_defaults attack: 4, release: 8, amp: 0.4, cutoff: 70
      play_chord chord(:D3, :m9), pan: 0.5
      sleep 8
      play_chord chord(:E3, :m9), pan: -0.5
      sleep 8
    end
  end
end

live_loop :bells do
  sync :ambient_pad
  with_fx :echo, mix: 0.5, decay: 6 do
    use_synth :fm
    use_synth_defaults attack: 0.5, release: 3, amp: 0.3
    play scale(:D5, :minor_pentatonic, num_octaves: 1).choose
    sleep [0.5, 1, 1.5].choose
  end
end

live_loop :background_arp do
  sync :ambient_pad
  with_fx :reverb, mix: 0.4, room: 0.7 do
    with_fx :slicer, phase: 1, wave: 0, mix: 0.2 do
      use_synth :pluck
      use_synth_defaults attack: 0.1, release: 1, amp: 0.2
      play_pattern_timed (scale :D4, :dorian, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      sleep 4
    end
  end
end
```

この修正済みコードでは、`:background_arp`の`live_loop`で`:dorian`スケールが使用されています。これで、エラーが発生せずに実行できるはずです。コードをSonic Piに貼り付けて、リラックスできるアンビエントな曲をお楽しみください。

## ユーザー:

最後のパートの音をもう少し控えめにして、もう少し工夫を加えてください。

## ChatGPT:

もちろんです。最後のパートの音を控えめにするために、`amp`（音量）を減らし、さらに工夫として、パートが8小節ごとに異なるスケールを使うように変更してみました。以下の修正済みコードをお試しください。

```ruby
use_bpm 60

live_loop :ambient_pad do
  with_fx :reverb, mix: 0.7, room: 0.8 do
    with_fx :slicer, phase: 2, wave: 1, mix: 0.3 do
      use_synth :dsaw
      use_synth_defaults attack: 4, release: 8, amp: 0.4, cutoff: 70
      play_chord chord(:D3, :m9), pan: 0.5
      sleep 8
      play_chord chord(:E3, :m9), pan: -0.5
      sleep 8
    end
  end
end

live_loop :bells do
  sync :ambient_pad
  with_fx :echo, mix: 0.5, decay: 6 do
    use_synth :fm
    use_synth_defaults attack: 0.5, release: 3, amp: 0.3
    play scale(:D5, :minor_pentatonic, num_octaves: 1).choose
    sleep [0.5, 1, 1.5].choose
  end
end

live_loop :background_arp do
  sync :ambient_pad
  with_fx :reverb, mix: 0.4, room: 0.7 do
    with_fx :slicer, phase: 1, wave: 0, mix: 0.2 do
      use_synth :pluck
      use_synth_defaults attack: 0.1, release: 1, amp: 0.1
      if (tick % 16) < 8
        play_pattern_timed (scale :D4, :dorian, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      else
        play_pattern_timed (scale :E4, :phrygian, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      end
      sleep 4
    end
  end
end
```

この修正済みコードでは、`:background_arp`の`live_loop`の`amp`を0.1に減らして音量を控えめにし、さらに8小節ごとに`:dorian`スケールと`:phrygian`スケールを交互に使うように変更しました。これにより、曲に新たな変化と複雑さが加わります。コードをSonic Piに貼り付けて、リラックスできるアンビエントな曲をお楽しみください。

## ユーザー:

最後のパートをもっと穏やかな音色に変えてください。

## ChatGPT:

もちろんです。最後のパートをもっと穏やかな音色にするために、シンセサイザーを`pluck`から`hollow`に変更し、リリース時間を増やして、音が長く響くようにしました。以下の修正済みコードをお試しください。

```ruby
use_bpm 60

live_loop :ambient_pad do
  with_fx :reverb, mix: 0.7, room: 0.8 do
    with_fx :slicer, phase: 2, wave: 1, mix: 0.3 do
      use_synth :dsaw
      use_synth_defaults attack: 4, release: 8, amp: 0.4, cutoff: 70
      play_chord chord(:D3, :m9), pan: 0.5
      sleep 8
      play_chord chord(:E3, :m9), pan: -0.5
      sleep 8
    end
  end
end

live_loop :bells do
  sync :ambient_pad
  with_fx :echo, mix: 0.5, decay: 6 do
    use_synth :fm
    use_synth_defaults attack: 0.5, release: 3, amp: 0.3
    play scale(:D5, :minor_pentatonic, num_octaves: 1).choose
    sleep [0.5, 1, 1.5].choose
  end
end

live_loop :background_arp do
  sync :ambient_pad
  with_fx :reverb, mix: 0.4, room: 0.7 do
    with_fx :slicer, phase: 1, wave: 0, mix: 0.2 do
      use_synth :hollow
      use_synth_defaults attack: 0.1, release: 3, amp: 0.1
      if (tick % 16) < 8
        play_pattern_timed (scale :D4, :dorian, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      else
        play_pattern_timed (scale :E4, :phrygian, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      end
      sleep 4
    end
  end
end
```

この修正済みコードでは、`:background_arp`の`live_loop`でシンセサイザーを`hollow`に変更し、リリース時間を3に増やして音が長く響くようにしました。これにより、曲が全体的により穏やかな雰囲気になります。コードをSonic Piに貼り付けて、リラックスできるアンビエントな曲をお楽しみください。

## ユーザー:

:bellsのパートの音量をかなり抑えて、もっと複雑で深く飽きないメロディーにしてください。

## ChatGPT:

もちろんです。`:bells`のパートの音量を抑えるために、`amp`を0.15に減らし、さらにメロディを複雑で深く飽きのこないものにするために、異なるスケールとリズムを使用しました。以下の修正済みコードをお試しください。

```ruby
use_bpm 60

live_loop :ambient_pad do
  with_fx :reverb, mix: 0.7, room: 0.8 do
    with_fx :slicer, phase: 2, wave: 1, mix: 0.3 do
      use_synth :dsaw
      use_synth_defaults attack: 4, release: 8, amp: 0.4, cutoff: 70
      play_chord chord(:D3, :m9), pan: 0.5
      sleep 8
      play_chord chord(:E3, :m9), pan: -0.5
      sleep 8
    end
  end
end

live_loop :bells do
  sync :ambient_pad
  with_fx :echo, mix: 0.5, decay: 6 do
    use_synth :fm
    use_synth_defaults attack: 0.2, release: 2, amp: 0.15
    if (tick % 16) < 8
      play scale(:D5, :minor_pentatonic, num_octaves: 1).choose, release: rrand(1, 2)
      sleep [0.5, 1, 1.5].choose
    else
      play scale(:D5, :mixolydian, num_octaves: 1).choose, release: rrand(1, 2)
      sleep [0.25, 0.5, 0.75, 1].choose
    end
  end
end

live_loop :background_arp do
  sync :ambient_pad
  with_fx :reverb, mix: 0.4, room: 0.7 do
    with_fx :slicer, phase: 1, wave: 0, mix: 0.2 do
      use_synth :hollow
      use_synth_defaults attack: 0.1, release: 3, amp: 0.1
      if (tick % 16) < 8
        play_pattern_timed (scale :D4, :dorian, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      else
        play_pattern_timed (scale :E4, :phrygian, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      end
      sleep 4
    end
  end
end
```

この修正済みコードでは、`:bells`の`live_loop`の`amp`を0.15に減らして音量を抑え、8小節ごとに`:minor_pentatonic`スケールと`:mixolydian`スケールを交互に使い、リズムパターンも変更しました。これにより、曲がより複

## ユーザー:

:bellsのパートの音量をかなり抑えて、もっと複雑で深く飽きないメロディーにしてください。

## ChatGPT:

もちろんです。`:bells`のパートの音量を抑えるために、`amp`を0.15に減らし、さらにメロディを複雑で深く飽きのこないものにするために、異なるスケールとリズムを使用しました。以下の修正済みコードをお試しください。

```ruby
use_bpm 60

live_loop :ambient_pad do
  with_fx :reverb, mix: 0.7, room: 0.8 do
    with_fx :slicer, phase: 2, wave: 1, mix: 0.3 do
      use_synth :dsaw
      use_synth_defaults attack: 4, release: 8, amp: 0.4, cutoff: 70
      play_chord chord(:D3, :m9), pan: 0.5
      sleep 8
      play_chord chord(:E3, :m9), pan: -0.5
      sleep 8
    end
  end
end

live_loop :bells do
  sync :ambient_pad
  with_fx :echo, mix: 0.5, decay: 6 do
    use_synth :fm
    use_synth_defaults attack: 0.2, release: 2, amp: 0.15
    if (tick % 16) < 8
      play scale(:D5, :minor_pentatonic, num_octaves: 1).choose, release: rrand(1, 2)
      sleep [0.5, 1, 1.5].choose
    else
      play scale(:D5, :mixolydian, num_octaves: 1).choose, release: rrand(1, 2)
      sleep [0.25, 0.5, 0.75, 1].choose
    end
  end
end

live_loop :background_arp do
  sync :ambient_pad
  with_fx :reverb, mix: 0.4, room: 0.7 do
    with_fx :slicer, phase: 1, wave: 0, mix: 0.2 do
      use_synth :hollow
      use_synth_defaults attack: 0.1, release: 3, amp: 0.1
      if (tick % 16) < 8
        play_pattern_timed (scale :D4, :dorian, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      else
        play_pattern_timed (scale :E4, :phrygian, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      end
      sleep 4
    end
  end
end
```

この修正済みコードでは、`:bells`の`live_loop`の`amp`を0.15に減らして音量を抑え、8小節ごとに`:minor_pentatonic`スケールと`:mixolydian`スケールを交互に使い、リズムパターンも変更しました。これにより、曲がより複

## ユーザー:

もう一つ軽やかなパートを追加してください。

## ChatGPT:

もちろんです。新しい軽やかなパートを追加するために、ピッチの高いシンセサイザーでシンプルなリズムを演奏する新しい`live_loop`を作成しました。以下のコードをお試しください。

```ruby
use_bpm 60

live_loop :ambient_pad do
  with_fx :reverb, mix: 0.7, room: 0.8 do
    with_fx :slicer, phase: 2, wave: 1, mix: 0.3 do
      use_synth :dsaw
      use_synth_defaults attack: 4, release: 8, amp: 0.4, cutoff: 70
      play_chord chord(:D3, :m9), pan: 0.5
      sleep 8
      play_chord chord(:E3, :m9), pan: -0.5
      sleep 8
    end
  end
end

live_loop :bells do
  sync :ambient_pad
  with_fx :echo, mix: 0.5, decay: 6 do
    use_synth :fm
    use_synth_defaults attack: 0.2, release: 2, amp: 0.15
    if (tick % 16) < 8
      play scale(:D5, :minor_pentatonic, num_octaves: 1).choose, release: rrand(1, 2)
      sleep [0.5, 1, 1.5].choose
    else
      play scale(:D5, :mixolydian, num_octaves: 1).choose, release: rrand(1, 2)
      sleep [0.25, 0.5, 0.75, 1].choose
    end
  end
end

live_loop :background_arp do
  sync :ambient_pad
  with_fx :reverb, mix: 0.4, room: 0.7 do
    with_fx :slicer, phase: 1, wave: 0, mix: 0.2 do
      use_synth :hollow
      use_synth_defaults attack: 0.1, release: 3, amp: 0.1
      if (tick % 16) < 8
        play_pattern_timed (scale :D4, :dorian, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      else
        play_pattern_timed (scale :E4, :phrygian, num_octaves: 2).shuffle, 0.25, pan: rrand(-0.5, 0.5)
      end
      sleep 4
    end
  end
end

live_loop :light_melody do
  sync :ambient_pad
  with_fx :reverb, mix: 0.3, room: 0.5 do
    with_fx :echo, mix: 0.4, decay: 2 do
      use_synth :piano
      use_synth_defaults amp: 0.2, attack: 0.05, release: 0.5
      play_pattern_timed (scale :D6, :mixolydian).shuffle, [1, 1.5, 0.5, 0.75].choose,

## ユーザー:

続き

## ChatGPT:

```　
pan: rrand(-0.5, 0.5)
    end
  end
end
```

このコードでは、新しい`:light_melody`の`live_loop`を追加し、`piano`シンセサイザーを使用して、軽やかなリズムを演奏しています。リバーブとエコーエフェクトを適用し、高いピッチの`:mixolydian`スケールを使ってメロディを生成しました。選択されたリズムパターンもさまざまで、楽曲に新たな軽やかさを追加しています。コードをSonic Piに貼り付けて、リラックスできるアンビエントな曲をお楽しみください。
