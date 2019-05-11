---
title: JD Edwards OneWorld アダプターでの文字列の位置を設定 |Microsoft Docs
description: Jdearglist ファイルは、JD Edwards OneWorld アダプターを使用して BizTalk Server オーケストレーションを更新します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f33941e997315a5e91e5c99f4e6dc4bd0d2b7aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393246"
---
# <a name="set-string-justification-in-jdearglist"></a>Jdearglist での位置の文字列の設定

## <a name="overview"></a>概要
特定の文字列引数として構成するのに右揃え (および左側に埋め込み) では、JD Edwards OneWorld の jdearglist.txt ファイル; にアクセスするどのようなビジネス機能を知る必要があります具体的には、呼び出したいビジネス関数のどのフィールドが必要です。  
  
 オーケストレーションのバインド (スキーマ) を生成する前に、jdearglist.txt を更新する必要があります。 Jdearglist.txt ファイルを更新するための手順が記載されている[文字列値の処理](../core/handling-string-values1.md)します。  
  
 監査ログに jdearglist.txt の警告メッセージを受信する場合に通知する、jdearglist.txt がないこと。 SalesOrder または PurchaseOrder ビジネス関数を実行する場合は、パスにファイルが必要または機能しません。  
  
## <a name="see-also"></a>参照  
[BizTalk Server 例外処理の使用](using-biztalk-server-exception-handling1.md)