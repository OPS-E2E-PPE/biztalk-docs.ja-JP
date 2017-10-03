---
title: "エラー - ループしない入力が複数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.multipleInputsWithoutLooping
ms.assetid: 7e55ad22-06a8-4a56-839d-a30b82819a68
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 93a8a11b25c3c1df52827bdbf4098f0cd37bdd8b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---multiple-inputs-without-looping"></a>エラー - ループしない入力が複数あります。
**エラー コード**  
  
 btm1004  
  
 **説明**  
  
 複数のリンクが、指定されたノードの先祖ノードのいずれかに接続されている場合にのみ有効ですが、送信先スキーマのノードに接続している、**ループ**functoid です。  
  
 **ユーザーの操作**  
  
 送信先スキーマの対象ノードへのリンクのうち 1 つを残して後のリンクをすべて削除するか、対象ノードの祖先ノードの 1 つをループ Functoid に接続します。