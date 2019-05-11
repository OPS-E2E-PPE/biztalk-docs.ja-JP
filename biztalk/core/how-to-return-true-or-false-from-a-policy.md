---
title: ポリシーから True または False を返す方法 |Microsoft Docs
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
ms.openlocfilehash: 093d58d97d6ecc2df842118b5a30f9858f4b4b96
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334902"
---
# <a name="how-to-return-true-or-false-from-a-policy"></a>ポリシーから True または False を返す方法
ポリシーの戻り値の型を直接指定することはできません。 ただし、ファクトの種類は次の 1 つをポリシーに渡す、このファクトの値を変更するポリシーが適用されて`true`または`false`、し、ポリシーの実行後に、プロパティ、要素、列の値を確認します。  
  
-   型のプロパティを使用して、.NET オブジェクト `Boolean`  
  
-   型の要素を持つ XML ドキュメント `Boolean`  
  
-   型の列を含むデータベース テーブル `Boolean`