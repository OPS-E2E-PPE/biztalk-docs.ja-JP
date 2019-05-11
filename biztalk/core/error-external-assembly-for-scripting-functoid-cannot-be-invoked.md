---
title: エラー - スクリプト Functoid の外部のアセンブリを呼び出すことができません。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.cannotInvokeExternalAssembly
ms.assetid: 30d97b05-2cbf-44a5-b219-3a5ae17fc597
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dcf4b387dd33900130e8aa5adff29b8de8d79ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348340"
---
# <a name="error---external-assembly-for-scripting-functoid-cannot-be-invoked"></a>エラー - スクリプト Functoid の外部のアセンブリを呼び出すことができません。
**エラー コード**  
  
 btm1067  
  
 **説明**  
  
 関連するに関連付けられている外部アセンブリ メソッド**Scripting** functoid を呼び出すことができません。 マップのコンパイルは必要ありませんがマップのテスト操作では、このような外部アセンブリがグローバル アセンブリ キャッシュ (GAC) に存在することが必要です。 通常、時間の操作を実行するには、外部アセンブリが GAC に存在することも必要です。  
  
 **ユーザーの操作**  
  
 外部のアセンブリによって、関連する参照されることを確認**Scripting** functoid は、GAC にします。