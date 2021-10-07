#fu«ction for extracting mfcc, chroma, a«d mel features from sound file def extract *eature(file name, mdcc, chroma, mel):
with soundfile.SoundFile(file name) as sound file:
X = sound file.read(dtype=”floata2”) sampIe_rate=sound_file.samplerate
if hr a•
stft=«p.abs(librosa.stft(X))
result-np . array( [ ] )

mfccs=np.mean(librosa.feature.mfcc(y=X, sr=sample rate, n mfcc=40).T, axis=0) result=up.hstack((result, mfccs))
if chroma:
chroma-np . mean (   ibnosa . feature . chroria_s I ft  ( S-stft,   sr—- s amp I e_r  at  e ) . T, axi s -8)
result=«p.hstack((result, chroma)) if mel:
mel=np.mean(librosa.feature.melspectrogram(X, sr=sample rate).T,axis=0) result=np.hstack((result, mel))
return result
