---
title: シングル サインオン:イベント 10507 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b02d8dfa-7655-471e-84af-e58d08c3cefd
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c147e2cbd5beb0e6c07519b35b700aa59b2b00dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398877"
---
# <a name="single-sign-on-event-10507"></a>シングル サインオン:イベント 10507
## <a name="details"></a>詳細  

|                 |                                                                 |
|-----------------|-----------------------------------------------------------------|
|  製品名   |                    エンタープライズ シングル サインオン                    |
| 製品バージョン |   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]    |
|    イベント ID     |                              10504                              |
|  イベント ソース   |                             ENTSSO                              |
|    コンポーネント    |                               該当なし                               |
|  シンボル名  |                 SSO_INFO_SERVICE_INSTALL_FAILED                 |
|  メッセージ テキスト   | SSO service.%r のインストールに失敗しました<br /><br /> エラー コード: %1 |

## <a name="explanation"></a>説明  
 このイベントは、ENTSSO サービスがインストールに失敗したことを示します。 このイベントは、エンタープライズ シングル サインオンの手動インストール時にのみ実行できます。  

## <a name="user-action"></a>ユーザーの操作  
 このイベントを解決するには、次の操作を行います。  

- ENTSSO または他のサービスから関連するエラーのアプリケーションとシステムの両方のイベント ログを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO のインストール](../core/installing-sso.md)  

- [Enterprise Single Sign-On の実装](../core/implementing-enterprise-single-sign-on.md)
