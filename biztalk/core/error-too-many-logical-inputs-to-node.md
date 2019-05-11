---
title: エラー - ノードへの論理入力が多すぎます |Microsoft Docs
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
ms.openlocfilehash: 4892eca0fc65fe281ab9464eba914603f7ab392b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65346309"
---
# <a name="error---too-many-logical-inputs-to-node"></a>エラー - ノードへの論理入力が多すぎます
**エラー コード**  
  
 btm1006  
  
 **説明**  
  
 多くへの入力リンクの数よりも、送信先スキーマのノードに接続している論理リンクがある、**ループ**functoid、対象ノードの祖先のノードに接続されています。 前者と後者の型のリンクの数が一致する必要があります。  
  
 **ユーザーの操作**  
  
 指定されたノードとリンクの数が接続されている作業のやり直し、**ループ**functoid が、祖先ノードに接続されている一致するものとします。