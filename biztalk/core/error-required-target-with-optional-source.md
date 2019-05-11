---
title: エラー - 必須ターゲットに省略可能なソース |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.reqdTargetWithOptionalSource
ms.assetid: 3f342011-4577-4682-8324-8296615d5194
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 942a73185c608df664fa41c3c44d9d1016f3bf41
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347005"
---
# <a name="error---required-target-with-optional-source"></a>エラー - 必須ターゲットに省略可能なソース
**エラー コード**  
  
 btm1001  
  
 **説明**  
  
 送信先スキーマの必須ノードのデータが、送信元スキーマの任意指定ノードから取得されています。 このため、有効なインスタンス メッセージの中に、マッピングできないものがある可能性があります。  
  
 **ユーザーの操作**  
  
 指定された送信元ノードと送信先ノードの特性が省略可能か必須かを確認します。これらのノードの特性は、同じにすることをお勧めします。