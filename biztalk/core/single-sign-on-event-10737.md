---
title: シングル サインオン:イベント 10737 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2102930b-8b1f-4d48-a14d-e8884dc7f9aa
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 522eac1a2a70b1518f35c58d82ede99d6a402af0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65270935"
---
# <a name="single-sign-on-event-10737"></a>シングル サインオン:イベント 10737
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                        |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                               エンタープライズ シングル サインオン                                                                                                |
| 製品バージョン |                                                                               [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                               |
|    イベント ID     |                                                                                                         10737                                                                                                          |
|  イベント ソース   |                                                                                                         ENTSSO                                                                                                         |
|    コンポーネント    |                                                                                                          該当なし                                                                                                           |
|  シンボル名  |                                                                                           SSO_WARN_PS_SET_EXTERNAL_PASSWORD                                                                                            |
|  メッセージ テキスト   | SSO database.%r 内の外部パスワードを更新できませんでした。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> アプリケーション名: % 3 %r<br /><br /> 外部アカウント: % 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO が SSO データベース内の外部パスワードの更新に失敗したことを示します。 さまざまな警告メッセージに示されているエラーの原因が考えられます場合によっては、この警告は、構成の問題を示す可能性があります。 またはマッピングが削除されているパスワードの変更プロセスの中にします。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- パスワードの変更を再試行してください。  

- 追加の試行も失敗する場合は、UI またはコマンド ライン ツールを使用して手動でパスワードを変更します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期](../core/password-synchronization2.md)
