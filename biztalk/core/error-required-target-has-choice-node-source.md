---
title: エラー - 必須ターゲットに選択ノードのソースが |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.reqdTargetHasChoiceNodeSource
ms.assetid: 5b5af999-d100-4e5d-a959-c8b11d574d3b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a33a5fc9bbcfe44e71b0caab6569279aeb9c32f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388468"
---
# <a name="error---required-target-has-choice-node-source"></a>エラー - 必須ターゲットに選択ノードのソース
**エラー コード**  
  
 btm1029  
  
 **説明**  
  
 送信先スキーマのノードが指定されたとして必要ですが、内にある送信元スキーマ内のノードにリンクされて、**選択肢**ノード。 入力インスタンス メッセージに、送信元スキーマのノードが表示されない、ため、ある可能性がありますいない必須ノードを送信先スキーマの作成元のソース。  
  
 **ユーザーの操作**  
  
 必要に応じて、省略可能な送信先スキーマのノードに変更か、または、すべての有効な入力インスタンス メッセージで発生する必要がある、送信先スキーマのノードのさまざまなソースを提供します。