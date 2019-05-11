---
title: エラー - 昇格させたプロパティ Max Occurs |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.promoPropMaxOccurs
ms.assetid: fc07367e-40f2-46e9-aeeb-bfa2498b1b37
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fcaf06dc0fccbf838c401343b3ce1e8f3b538ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65347056"
---
# <a name="error---promoted-property-max-occurs"></a>エラー - 昇格させたプロパティ Max Occurs します。
**エラー コード**  
  
 BEC2002  
  
 **説明**  
  
 設定、 **Max Occurs**またはその先祖ノードの 1 つの昇格を試みているノードのプロパティがプロパティの昇格と互換性がありません。 インスタンス メッセージ内で複数回出現可能なノード プロパティの昇格は許可されていません。 そのため、 **Max Occurs**ルート ノードに昇格するノードからすべてのノードのプロパティを 1 に設定する必要があります。  
  
 **ユーザーの操作**  
  
 いることを確認、 **Max Occurs**昇格するノードとその祖先のノードのすべてのプロパティが 1 つ (1) に設定します。