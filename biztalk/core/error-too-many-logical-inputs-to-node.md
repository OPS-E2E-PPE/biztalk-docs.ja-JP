---
title: エラー - ノードへの論理入力が多すぎます |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tooManyLogicalInputsToNode
ms.assetid: 9295d6a2-702d-4cf3-8f5d-26ba63b9fce0
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e363d79a2b013b8e90533c4e6e36cff5b5798b77
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241706"
---
# <a name="error---too-many-logical-inputs-to-node"></a>エラー - ノードへの論理入力が多すぎます
**エラー コード**  
  
 btm1006  
  
 **説明**  
  
 入力リンクの数よりも、送信先スキーマのノードに接続している論理リンク数がある、**ループ**functoid のノードの祖先のノードに接続されています。 この 2 種類のリンクの数は、一致している必要があります。  
  
 **ユーザーの操作**  
  
 作業のやり直しのノードにされ、接続されているリンクの数、**ループ**functoid が、祖先ノードに接続されている一致するものとします。