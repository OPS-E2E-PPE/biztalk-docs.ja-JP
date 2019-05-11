---
title: シングル サインオン:イベント 10739 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1039c832-80ff-4cc2-97b4-2671672b6b12
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0acbcb7433c5332dbcb7e183873ea19e660578db
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291770"
---
# <a name="single-sign-on-event-10739"></a>シングル サインオン:イベント 10739
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                               エンタープライズ シングル サインオン                                                                               |
| 製品バージョン |                                                              [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                               |
|    イベント ID     |                                                                                         10739                                                                                         |
|  イベント ソース   |                                                                                        ENTSSO                                                                                         |
|    コンポーネント    |                                                                                          該当なし                                                                                          |
|  シンボル名  |                                                                       SSO_WARN_PS_SET_WINDOWS_PASSWORD_ADAPTER                                                                        |
|  メッセージ テキスト   | SSO database.%r 内の Windows パスワードを更新できませんでした。<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: % 2 %r<br /><br /> Windows アカウント: %3\\% 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、SSO が SSO データベース内の Windows パスワードを更新に失敗したことを示します。 さまざまな警告メッセージに示されているエラーの原因が考えられます場合によっては、この警告は、構成の問題を示す可能性があります。 またはマッピングが削除されているパスワードの変更プロセスの中にします。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の操作を行います。  

- パスワードの変更を再試行してください。  

- 追加の試行も失敗する場合は、UI またはコマンド ライン ツールを使用して手動でパスワードを変更します。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期](../core/password-synchronization2.md)
