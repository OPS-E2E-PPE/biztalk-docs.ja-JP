---
title: エラー - XSLT スクリプト Functoid の子がコードを生成する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.xsltScriptingChildrenGenCode
ms.assetid: 9cdac362-177f-445e-904b-aa6a9b1eb46f
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4111d359c0a764c92fc9736fdd2fcbc879252274
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65388988"
---
# <a name="error---children-of-xslt-scripting-functoid-generate-code"></a>エラー - XSLT スクリプト Functoid の子がコードを生成します。
**エラー コード**  
  
 btm1063  
  
 **説明**  
  
 使用と矛盾するシナリオを**Scripting**マップに functoid のインライン XSLT または XSLT 呼び出しテンプレートを使用するように構成が見つかりました。 送信先スキーマ、このような出力にリンクされているノードの子孫のノードで、 **Scripting** functoid は自身の XSLT コードを生成しようとしています。  
  
 **ユーザーの操作**  
  
 非互換性を関連する使用状況を変更することで削除**Scripting** functoid を変更するか、子ノードが自身の XSLT コードを生成しないようにします。