---
title: エラー - ループしない入力が複数 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.multipleInputsWithoutLooping
ms.assetid: 7e55ad22-06a8-4a56-839d-a30b82819a68
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ce2cdef2a80e6e58b635cf9fed0dbc52c817e0d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347312"
---
# <a name="error---multiple-inputs-without-looping"></a>エラー - ループしない入力が複数
**エラー コード**  
  
 btm1004  
  
 **説明**  
  
 複数のリンクは、対象のノードの先祖ノードのいずれかに接続されている場合にのみ有効ですが、送信先スキーマのノードに接続している、**ループ**functoid。  
  
 **ユーザーの操作**  
  
 送信先スキーマのノードへのリンクの 1 つだけ削除するか、対象のノードの先祖ノードのいずれかのループ functoid への接続します。