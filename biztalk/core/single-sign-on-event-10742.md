---
title: シングル サインオン:イベント 10742 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba62f878-ed12-421f-81ea-9285b2624fe9
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: afe1849acf5ad6cbafb948465a0cbc8f8f06ba84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400573"
---
# <a name="single-sign-on-event-10742"></a>シングル サインオン:イベント 10742
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                                                                                                                            |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                                                                         エンタープライズ シングル サインオン                                                                                                                                          |
| 製品バージョン |                                                                                                                         [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                                         |
|    イベント ID     |                                                                                                                                                   10742                                                                                                                                                    |
|  イベント ソース   |                                                                                                                                                   ENTSSO                                                                                                                                                   |
|    コンポーネント    |                                                                                                                                                    該当なし                                                                                                                                                     |
|  シンボル名  |                                                                                                                                         SSO_WARN_NO_UPDATE_ADAPTER                                                                                                                                         |
|  メッセージ テキスト   | クライアント ユーザーは adapter.%r を更新するには、SSO 管理者アカウントまたはアプリケーション管理者アカウントのメンバーである必要があります。<br /><br /> クライアント ユーザー: 1 %r<br /><br /> SSO 管理者: % 2 %r<br /><br /> アプリケーション管理者: % 3 %r<br /><br /> アダプター: % 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 この警告イベントは、指定したアダプターを更新しようとが行われたが、使用するユーザー アカウントが SSO 管理者アカウントまたはアプリケーション管理者アカウントのメンバーではないために、完了できませんでしたを示します。  

## <a name="user-action"></a>ユーザーの操作  
 この警告を解決するには、次の 1 つ以上の操作を行います。  

- SSO 管理者アカウントまたはアプリケーション管理者アカウントにユーザー アカウントを追加します。  

- 更新プログラムを再試行してください。  

  詳細については、次のリソースを参照してください。  

- [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)
