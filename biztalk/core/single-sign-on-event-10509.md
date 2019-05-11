---
title: シングル サインオン:イベント 10509 |Microsoft Docs
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
ms.openlocfilehash: 2911358dd326c5fa7f2673567f53805edb898de0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243419"
---
# <a name="single-sign-on-event-10509"></a>シングル サインオン:イベント 10509
## <a name="details"></a>詳細  

|                 |                                                                |
|-----------------|----------------------------------------------------------------|
|  製品名   |                   エンタープライズ シングル サインオン                    |
| 製品バージョン |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    イベント ID     |                             10509                              |
|  イベント ソース   |                             ENTSSO                             |
|    コンポーネント    |                              該当なし                               |
|  シンボル名  |                 SSO_INFO_SERVICE_REMOVE_FAILED                 |
|  メッセージ テキスト   | SSO service.%r を削除できませんでした。<br /><br /> エラー コード: %1 |

## <a name="explanation"></a>説明  
 このイベントは、ENTSSO サービスがアンインストールに失敗したことを示します。 このイベントは、エンタープライズ シングル サインオンの手動アンインストール中にのみ実行できます。  

## <a name="user-action"></a>ユーザーの操作  
 このイベントを解決するには、次の操作を行います。  

- ENTSSO または他のサービスから関連するエラーのアプリケーションとシステムの両方のイベント ログを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO のインストール](../core/installing-sso.md)  

- [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)
