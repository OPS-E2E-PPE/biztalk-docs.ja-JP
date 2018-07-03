---
title: 'シングル サインオン: イベント 10509 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f906823f-db3f-45fc-bf61-cbe6a9566bd7
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 12e21d19a4504ecebd14060c784a19f5f7446035
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968723"
---
# <a name="single-sign-on-event-10509"></a>シングル サインオン: イベント 10509
## <a name="details"></a>詳細  

|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  製品名   |                   エンタープライズ シングル サインオン                    |
| 製品バージョン |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    イベント ID     |                             10509                              |
|  イベント ソース   |                             ENTSSO                             |
|    コンポーネント    |                              N\A                               |
|  シンボル名  |                 SSO_INFO_SERVICE_REMOVE_FAILED                 |
|  メッセージ テキスト   | SSO サービスを削除できませんでした。%r<br /><br /> エラー コード: %1 |

## <a name="explanation"></a>説明  
 このイベントは、ENTSSO サービスのアンインストールが失敗したことを示します。 このイベントは、エンタープライズ シングル サインオンの手動アンインストールの間にのみ発生します。  

## <a name="user-action"></a>ユーザーの操作  
 このイベントを解決するには、次の手順を実行します。  

- ENTSSO または他のサービスからの関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [SSO のインストール](../core/installing-sso.md)  

- [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)
