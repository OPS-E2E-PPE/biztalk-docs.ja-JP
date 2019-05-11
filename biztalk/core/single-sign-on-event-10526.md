---
title: シングル サインオン:イベント 10526 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f72d466-8b63-453c-b608-f9d64f635f65
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 924f6dee79b51740c62b302a0e57371fdd060470
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394324"
---
# <a name="single-sign-on-event-10526"></a>シングル サインオン:イベント 10526
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                     エンタープライズ シングル サインオン                                                                     |
| 製品バージョン |                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                     |
|    イベント ID     |                                                                               10526                                                                               |
|  イベント ソース   |                                                                              ENTSSO                                                                               |
|    コンポーネント    |                                                                                該当なし                                                                                |
|  シンボル名  |                                                                 SSO_ERROR_GENERATE_SECRET_FAILED                                                                  |
|  メッセージ テキスト   | 新しいマスター secret.%r を生成できませんでした。<br /><br /> クライアント ユーザー: 1 %r<br /><br /> クライアント コンピューター: %2 %r<br /><br /> 追跡 ID: % 3 %r<br /><br /> エラー コード: %4 |

## <a name="explanation"></a>説明  
 このエラー イベントは、新しいマスター シークレットを生成するユーザーの試行が失敗したことを示します。 原因としては、アクセス許可 (マスター シークレットを生成するのには、SSO 管理者である必要があります) の問題またはバックアップ ファイルに、マスター シークレットの書き込みに問題があった可能性があります。 このような場合があります関連するメッセージ、アプリケーション イベント ログ。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、以下の 1 つ以上の操作を実行します。  

- アプリケーション イベント ログの関連するイベントまたはエラーを確認します。  

- 適切な SSO 管理者のアクセス許可があることを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  

- [マスター シークレットの管理](../core/managing-the-master-secret.md)
