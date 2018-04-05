---
title: エラー - XSLT スクリプト Functoid の子がコードを生成します |Microsoft ドキュメント
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
ms.openlocfilehash: 810fe9befecd9bbd1a15468ca714177900450cb7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---children-of-xslt-scripting-functoid-generate-code"></a>エラー - XSLT スクリプト Functoid の子がコードを生成します
**エラー コード**  
  
 btm1063  
  
 **説明**  
  
 使用と矛盾するシナリオ、**スクリプト**インライン XSLT または XSLT 呼び出しテンプレートを使用するように構成されている functoid マップが見つかりました。 送信先スキーマ、このような出力にリンクされているノードの子孫のノードで、**スクリプト**functoid は、自身の XSLT コードを生成しようとしています。  
  
 **ユーザーの操作**  
  
 関連の使用法を変更することで、非互換性を削除する**スクリプト**functoid を変更するか、子ノードが自身の XSLT コードを生成しないようにします。