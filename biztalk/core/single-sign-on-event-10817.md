---
title: 'シングル サインオン: イベント 10817 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f1668b81-e7f4-46d2-aebe-47007f70372b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c94f677ccd14dd821886210f9e4c55efd754a404
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276746"
---
# <a name="single-sign-on-event-10817"></a>シングル サインオン: イベント 10817
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10817|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_NOTIFICATION_NOT_FOUND|  
|メッセージ テキスト|指定された通知が見つかりませんでした。|  
  
## <a name="explanation"></a>説明  
 パスワード変更で指定された通知の GUID が見つかりません。  
  
## <a name="user-action"></a>ユーザーの操作  
 このパスワード同期アダプターの構成を調べて、通知の正しい GUID を確認します。