---
title: エラー - 昇格させたプロパティ Max Occurs |Microsoft ドキュメント
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
ms.openlocfilehash: a9c8395757d19eff5241d47c31b15409a00b6faf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239866"
---
# <a name="error---promoted-property-max-occurs"></a>エラー - 昇格させたプロパティ Max Occurs します。
**エラー コード**  
  
 BEC2002  
  
 **説明**  
  
 設定、 **Max Occurs** 、昇格するノードまたはその先祖ノードのいずれかのプロパティがプロパティの昇格と互換性がありません。 インスタンス メッセージに複数回出現可能なノードでは、プロパティの昇格は許可されていません。 したがって、 **Max Occurs**ルート ノードに昇格するノードからすべてのノードのプロパティを 1 に設定する必要があります。  
  
 **ユーザーの操作**  
  
 いることを確認、 **Max Occurs**昇格するノードとそのすべての先祖ノードのプロパティが 1 つ (1) に設定します。