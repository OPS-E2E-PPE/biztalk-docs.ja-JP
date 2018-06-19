---
title: 'シングル サインオン: イベント 10507 |Microsoft ドキュメント'
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
ms.openlocfilehash: f9f184acaddf64a68b38211c84c86f418af42adf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269930"
---
# <a name="single-sign-on-event-10507"></a>シングル サインオン: イベント 10507
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10504|  
|イベント ソース|ENTSSO|  
|コンポーネント|N\A|  
|シンボル名|SSO_INFO_SERVICE_INSTALL_FAILED|  
|メッセージ テキスト|SSO サービスをインストールできませんでした。%r<br /><br /> エラー コード: %1|  
  
## <a name="explanation"></a>説明  
 このイベントは、ENTSSO サービスをインストールできなかったことを示します。 このイベントは、エンタープライズ シングル サインオンの手動でのインストール中にのみ発生する可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このイベントを解決するには、次の手順を実行します。  
  
-   ENTSSO または他のサービスからの関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。  
  
 詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   
  
-   [SSO のインストール](../core/installing-sso.md)  
  
-   [エンタープライズ シングル サインオンを実装します。](../core/implementing-enterprise-single-sign-on.md)