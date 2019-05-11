---
title: シングル サインオン:イベント 10586 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7d480e9-dc34-44ac-9272-0caf80237bd9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 757c84a4affa65493428cabd3fdb955f5415d234
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65271041"
---
# <a name="single-sign-on-event-10586"></a>シングル サインオン:イベント 10586
## <a name="details"></a>詳細  
  
|                 |                                                             |
|-----------------|-------------------------------------------------------------|
|  製品名   |                  エンタープライズ シングル サインオン                  |
| 製品バージョン | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]  |
|    イベント ID     |                            10586                            |
|  イベント ソース   |                           ENTSSO                            |
|    コンポーネント    |                             なし                             |
|  シンボル名  |                   SSO_WARN_CRED_CACHE_OFF                   |
|  メッセージ テキスト   | この SSO サーバーの資格情報キャッシュを無効にされています。 |
  
## <a name="explanation"></a>説明  
 一般に、有効になっている資格情報キャッシュが無効になりました。 システム管理者だけでは、有効にしたり、資格情報キャッシュを無効にすることができます。 資格情報キャッシュを無効にすることがありますになります、ENTSSO システムからの最新の資格情報が、パフォーマンス低下することできます。  
  
## <a name="user-action"></a>ユーザーの操作  
 資格情報キャッシュを再度有効にするには、方法アプリケーション プロパティ テーブルを参照してください。 [SSO 関連アプリケーション](../core/sso-affiliate-applications.md)します。