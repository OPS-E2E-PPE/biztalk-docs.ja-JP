---
title: "エラー - 必須ターゲットに選択ノードのソースは |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.reqdTargetHasChoiceNodeSource
ms.assetid: 5b5af999-d100-4e5d-a959-c8b11d574d3b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91c9ad912b03bbb475efcc9eb8207a388400b43b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---required-target-has-choice-node-source"></a>エラー - 必須ターゲットに選択ノードのソース
**エラー コード**  
  
 btm1029  
  
 **説明**  
  
 送信先スキーマのノードが指定されて、必須として内にある送信元スキーマ内のノードにリンクされて、**選択肢**ノード。 入力インスタンス メッセージには送信元スキーマのノードが表示されていないため、送信先スキーマに必須ノードを作成するための送信元が存在しない可能性があります。  
  
 **ユーザーの操作**  
  
 適宜、送信先スキーマの対象のノードを省略可能に変更するか、送信先スキーマのノードに、有効なすべての入力インスタンス メッセージに表示される別の送信元を設定します。