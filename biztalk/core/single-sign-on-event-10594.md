---
title: 'シングル サインオン: イベント 10594 |Microsoft Docs'
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
ms.openlocfilehash: ba733d9a919b2af09824242a48a2fa85af8ab481
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004762"
---
# <a name="single-sign-on-event-10594"></a>シングル サインオン: イベント 10594
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                                            |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                 エンタープライズ シングル サインオン                                                                                  |
| 製品バージョン |                                                                 [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                 |
|    イベント ID     |                                                                                           10594                                                                                            |
|  イベント ソース   |                                                                                           ENTSSO                                                                                           |
|    コンポーネント    |                                                                                            なし                                                                                             |
|  シンボル名  |                                                                              SSO_WARN_TICKET_VALIDATE_FAILED                                                                               |
|  メッセージ テキスト   | チケットの検証に失敗しました。 送信者名はチケット発行者名と一致している必要があります。%r<br /><br /> アプリケーション名: %1 %r<br /><br /> %2 のチケットの発行元: %r<br /><br /> 送信者名: %3 |
  
## <a name="explanation"></a>説明  
 チケットを検証するには、(警告メッセージに表示される) "チケット発行者" フィールドと "送信者名" フィールドが一致している必要があります。 しかし、メッセージが BizTalk で信頼されていないホストを介して送信される場合、"送信者名" が BizTalk で信頼されていないホストの名前に変更され、チケットは検証されません。  
  
## <a name="user-action"></a>ユーザーの操作  
 エンタープライズ シングル サインオンを使用している場合は、メッセージが BizTalk で信頼されているホストのみを介して送信されていることを確認します。 メッセージのデータ改ざんのリスクが軽減されます。  
  
 使用環境のシナリオにおけるセキュリティの意味を十分に理解している場合は、このアプリケーションの検証を無効にすることもできます。 検証は管理オプションであり、システム全体で無効にすることも、この特定のアプリケーションについてのみ無効にすることもできます。