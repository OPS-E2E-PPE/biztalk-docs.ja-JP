---
title: 'シングル サインオン: イベント 10594 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1f4c6041-39a8-49bc-b39e-66cb6eb2efae
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 804b2616080ceee0b6a31f7623e19e05c11481f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270562"
---
# <a name="single-sign-on-event-10594"></a>シングル サインオン: イベント 10594
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10594|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_TICKET_VALIDATE_FAILED|  
|メッセージ テキスト|チケットの検証に失敗しました。 送信者名はチケット発行者名と一致している必要があります。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> %2 のによってチケットが発行された %r。<br /><br /> 送信者名: %3|  
  
## <a name="explanation"></a>説明  
 チケットを検証するには、(警告メッセージに表示される) "チケット発行者" フィールドと "送信者名" フィールドが一致している必要があります。 しかし、メッセージが BizTalk で信頼されていないホストを介して送信される場合、"送信者名" が BizTalk で信頼されていないホストの名前に変更され、チケットは検証されません。  
  
## <a name="user-action"></a>ユーザーの操作  
 エンタープライズ シングル サインオンを使用している場合は、メッセージが BizTalk で信頼されているホストのみを介して送信されていることを確認します。 メッセージのデータ改ざんのリスクが軽減されます。  
  
 使用環境のシナリオにおけるセキュリティの意味を十分に理解している場合は、このアプリケーションの検証を無効にすることもできます。 検証は管理オプションであり、システム全体で無効にすることも、この特定のアプリケーションについてのみ無効にすることもできます。