---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"
date: {{ .Date }}
draft: true
description: "Một câu tóm tắt bài, hiện trên thẻ bài và Google."
categories: ["Món ngon"]   # chọn 1: Món ngon / Sách hay / Con cái / Chuyện hằng ngày / Quan điểm sống
tags: ["the-1", "the-2"]
place: "Ở đâu"
mood: "Tâm trạng"
products: []                 # id món đồ trong data/products.yaml
places: []                   # id quán trong data/places.yaml
sample: false
---

Mở bài bằng một câu chuyện thật của bạn...

## Ý chính 1

{{< nhanqua >}}

## Ý chính 2

{{< sanpham id="coc-su-men-ran" >}}
