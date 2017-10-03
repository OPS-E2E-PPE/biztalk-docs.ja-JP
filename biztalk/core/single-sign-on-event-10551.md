---
title: "シングル サインオン: イベント 10551 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 33434989-08d8-4d13-a3cc-4c5543add69c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30c4b315744749d232c30f4cc28c4d297a0f5243
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10551"></a>シングル サインオン: イベント 10551
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10551|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_INVALID_USER|  
|メッセージ テキスト|指定したユーザーがこのアプリケーションで有効ではないため、マッピングを作成できませんでした。%r<br /><br /> ドメイン名: %1 %r<br /><br /> ユーザー名: %2 %r<br /><br /> アプリケーション名: %3 %r<br /><br /> アプリケーション ユーザー: %4|  
  
## <a name="explanation"></a>説明  
 指定されたユーザーが有効ではありません。 これは入力の誤りである可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 警告情報に示されているユーザー名を調べて正しいことを確認し、マッピングを再作成します。