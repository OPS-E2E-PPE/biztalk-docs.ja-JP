---
title: シングル サインオン:イベント 10541 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7e206158-5652-453c-91ac-9a75ab02809a
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7a30d3c2221632d4dd9d050067f8fc9094d37d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65250287"
---
# <a name="single-sign-on-event-10541"></a>シングル サインオン:イベント 10541
## <a name="details"></a>詳細  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  製品名   |                 エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    イベント ID     |                           10541                            |
|  イベント ソース   |                           ENTSSO                           |
|    コンポーネント    |                             CO                             |
|  シンボル名  |               SSO_WARN_SSO_TICKETS_VALIDATED               |
|  メッセージ テキスト   |    検証を行わず、チケットを引き換えることはできません。     |

## <a name="explanation"></a>説明  
 この警告イベントは、検証を行わず SSO チケットを引き換えることができないことを示します。 SSO チケットを引き換えるときに検証したりできます検証されません。 検証では、BizTalk メッセージ内のユーザーの名前を持つ、チケットを発行したユーザーの名前を比較することによってセキュリティが向上します。 名前が同じではない場合は、検証が失敗します。 BizTalk メッセージのフロー、信頼されていないホストを介して、ときに、信頼されていないホストに、BizTalk メッセージ内のユーザーの名前が変更されます。 検証では、BizTalk メッセージが信頼されたホストでのみフローされたことを確認します。 このメッセージは意味 (SSO システム オプションの設定による)、SSO システム レベルで検証が必要ですが、呼び出し元によって検証情報が指定されていません。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

- BizTalk Server を使用している場合は、メッセージが 信頼されたホストのみを介して送信されていることを確認します。 これにより、メッセージのデータの改ざんのリスクが低減されます。  

- 自分のシナリオにより、このアプリケーションの検証をオフにします。 検証は、管理オプションであり、システムまたはこの特定のアプリケーションに対してだけ、オフにすることです。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO チケット](../core/sso-tickets.md)  

- [関連アプリケーションのプロパティを一覧表示する方法](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)
