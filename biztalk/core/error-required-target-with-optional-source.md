---
title: エラー - 必須ターゲットに省略可能なソース |Microsoft ドキュメント
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
ms.openlocfilehash: 76dd96f61766a475db6385e306bc64bc36db4fcf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241402"
---
# <a name="error---required-target-with-optional-source"></a>エラー - 必須ターゲットに省略可能なソース
**エラー コード**  
  
 btm1001  
  
 **説明**  
  
 送信先スキーマの必須ノードのデータが、送信元スキーマの任意指定ノードから取得されています。 このため、有効なインスタンス メッセージの中に、マッピングできないものがある可能性があります。  
  
 **ユーザーの操作**  
  
 指定された送信元ノードと送信先ノードの特性が省略可能か必須かを確認します。これらのノードの特性は、同じにすることをお勧めします。