---
title: "エラー - ノードへのデータ入力が多すぎます |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.tooManyDataInputsToNode
ms.assetid: 176805f0-2d6d-4072-b866-132b98c7e4b5
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9e465f861c4048708f41ea86f04ffd52375dec9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---too-many-data-inputs-to-node"></a>エラー - ノードへのデータ入力が多すぎます
**エラー コード**  
  
 btm1005  
  
 **説明**  
  
 多くへの入力リンクの数よりも、送信先スキーマのノードに接続しているリンクがある、**ループ**functoid のノードの祖先のノードに接続されています。 この 2 種類のリンクの数は、一致している必要があります。  
  
 **ユーザーの操作**  
  
 作業のやり直しのノードにされ、接続されているリンクの数、**ループ**functoid が、祖先ノードに接続されている一致するものとします。