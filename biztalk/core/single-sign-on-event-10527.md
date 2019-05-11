---
title: シングル サインオン:イベント 10527 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40995ad8-9f74-4e96-863d-427e23025ba1
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57f5ac8452d96e3af54ff4d5cfc21f6664435bc6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262508"
---
# <a name="single-sign-on-event-10527"></a>シングル サインオン:イベント 10527
## <a name="details"></a>詳細  

|                 |                                                                                                                                                                                                     |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                                      エンタープライズ シングル サインオン                                                                                      |
| 製品バージョン |                                                                     [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                      |
|    イベント ID     |                                                                                                10527                                                                                                |
|  イベント ソース   |                                                                                               ENTSSO                                                                                                |
|    コンポーネント    |                                                                                                  0                                                                                                  |
|  シンボル名  |                                                                                     SSO_ERROR_GET_SECRET_FAILED                                                                                     |
|  メッセージ テキスト   | マスター シークレット failed.%r を取得する要求<br /><br /> シークレット番号: % 1 %r<br /><br /> クライアント ユーザー: % 2 %r<br /><br /> クライアント コンピューターの場合: % 3 %r<br /><br /> 追跡 ID: % 4 %r<br /><br /> エラー コード: %5 |

## <a name="explanation"></a>説明  
 このエラー イベントは、マスター シークレットを取得する要求が失敗したことを示します。 このような場合があります関連するメッセージ、アプリケーション イベント ログ。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- アプリケーション イベント ログの関連するイベントまたはエラーを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [マスター シークレットを生成する方法](../core/how-to-generate-the-master-secret.md)  

- [マスター シークレットの管理](../core/managing-the-master-secret.md)
