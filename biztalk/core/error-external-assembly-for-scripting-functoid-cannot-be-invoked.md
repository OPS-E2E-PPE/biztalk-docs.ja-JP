---
title: "エラー - スクリプト Functoid の外部アセンブリを呼び出すことができません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.cannotInvokeExternalAssembly
ms.assetid: 30d97b05-2cbf-44a5-b219-3a5ae17fc597
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f6df36a955f2f40da35368fd72fd2d1fcbb7b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---external-assembly-for-scripting-functoid-cannot-be-invoked"></a>エラー - スクリプト Functoid の外部アセンブリを呼び出すことができません。
**エラー コード**  
  
 btm1067  
  
 **説明**  
  
 関連するに関連付けられている外部アセンブリ メソッド**スクリプト**functoid を呼び出すことができません。 このような外部アセンブリは、マップのコンパイルには必要ありませんが、マップのテストの操作では、グローバル アセンブリ キャッシュ (GAC) に存在する必要があります。 通常、ランタイム操作でも、外部アセンブリが GAC に存在する必要があります。  
  
 **ユーザーの操作**  
  
 関連するによって参照される外部アセンブリを確認してください**スクリプト**functoid が GAC にします。