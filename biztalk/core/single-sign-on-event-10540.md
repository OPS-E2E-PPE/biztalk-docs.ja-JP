---
title: シングル サインオン:イベント 10540 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ce91ff30-3d68-4c5f-a955-5c426e94d917
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd18184dbf06934600231a6bbb75abdc1709f5ec
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243408"
---
# <a name="single-sign-on-event-10540"></a>シングル サインオン:イベント 10540
## <a name="details"></a>詳細  

|                 |                                                                                  |
|-----------------|----------------------------------------------------------------------------------|
|  製品名   |                            エンタープライズ シングル サインオン                             |
| 製品バージョン |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]            |
|    イベント ID     |                                      10540                                       |
|  イベント ソース   |                                      ENTSSO                                      |
|    コンポーネント    |                                        CO                                        |
|  シンボル名  |                         SSO_WARN_APP_TICKETS_NOT_ALLOWED                         |
|  メッセージ テキスト   | この application.%r チケットが有効でないです。<br /><br /> アプリケーション名: %1 |

## <a name="explanation"></a>説明  
 この警告イベントは、チケット機能が有効になっていないこのアプリケーションを示します。 SSO チケットの使用は、SSO アプリケーションごとの省略可能な機能です。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- この SSO アプリケーションのチケットを有効にする、アプリケーション管理者に問い合わせてください。 これ行う SSO 管理ツール (GUI またはコマンドライン) を使用します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO チケット](../core/sso-tickets.md)  

- [関連アプリケーションのプロパティを一覧表示する方法](../core/how-to-list-the-properties-of-an-affiliate-application.md)  

- [関連アプリケーションのプロパティを更新する方法](../core/how-to-update-the-properties-of-an-affiliate-application.md)
