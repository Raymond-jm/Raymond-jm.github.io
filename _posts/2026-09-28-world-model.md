---
title: World Model(Ha & Schmidhuber, 2018)
date: 2026-09-28
categories: [World Model, Reinforcement Learning]
tags: [RL, VAE]
math: true
---


템플릿

$$ 
V(s) = \max_a \sum_{s'} P(s'|s,a)\,[R(s,a,s') + \gamma V(s')] 
$$

VAE(Variational Autoencoder)
이미지 x 가 인코더를 거쳐서 작은 벡터 z가 되고 다시 디코더를 거쳐 복원 이미지 $$ \hat{x} $$
 