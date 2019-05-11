---
title: エラー - ノードへのデータ入力が多すぎます |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.tooManyDataInputsToNode
ms.assetid: 176805f0-2d6d-4072-b866-132b98c7e4b5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3c5674e4a4dc0c18556b61ff49a761e89d7891dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388337"
---
# <a name="error---too-many-data-inputs-to-node"></a>エラー - ノードへのデータ入力が多すぎます
**エラー コード**  
  
 btm1005  
  
 **説明**  
  
 多くへの入力リンクの数よりも、送信先スキーマのノードに接続しているリンクがある、**ループ**functoid、対象ノードの祖先のノードに接続されています。 前者と後者の型のリンクの数が一致する必要があります。  
  
 **ユーザーの操作**  
  
 指定されたノードとリンクの数が接続されている作業のやり直し、**ループ**functoid が、祖先ノードに接続されている一致するものとします。