---
title: ポリシーから True または False を返す方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5a7bb9b2-14aa-44e7-a290-e49bf53bc594
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 281d5ab7648545f2e0616095f3c535d7d109136f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254410"
---
# <a name="how-to-return-true-or-false-from-a-policy"></a>ポリシーから True または False を返す方法
ポリシーで戻り値の型を直接指定することはできません。 ただし、次に示すファクトの種類の 1 つをポリシーに渡し、このファクトの値をポリシーで `true` または `false` に変更して、ポリシーの実行後にプロパティ、要素、または列の値を確認することができます。  
  
-   `Boolean` 型のプロパティを持つ .NET オブジェクト  
  
-   `Boolean` 型の要素を持つ XML ドキュメント  
  
-   `Boolean` 型の列を持つデータベース テーブル