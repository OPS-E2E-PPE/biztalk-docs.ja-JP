---
title: シングル サインオン:イベント 10652 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ae7fe452-bcec-4722-8ec6-78d4fe462a0a
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df470103391e41cdac109e5b58af0514d402f04a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397658"
---
# <a name="single-sign-on-event-10652"></a>シングル サインオン:イベント 10652
## <a name="details"></a>詳細  

|                 |                                                                           |
|-----------------|---------------------------------------------------------------------------|
|  製品名   |                         エンタープライズ シングル サインオン                         |
| 製品バージョン |        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]         |
|    イベント ID     |                                   10652                                   |
|  イベント ソース   |                                  ENTSSO                                   |
|    コンポーネント    |                                    該当なし                                    |
|  シンボル名  |                   SSO_ERROR_PASSWORD_SYNC_START_FAILED                    |
|  メッセージ テキスト   | Initialize.%r にパスワード同期サービスが失敗しました<br /><br /> エラー コード: %1 |

## <a name="explanation"></a>説明  
 このエラー イベントは、例外が原因で、パスワード同期サービスを開始できなかったことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- ENTSSO または他のサービスから関連するエラーのアプリケーションとシステムの両方のイベント ログを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [パスワード同期](../core/password-synchronization2.md)
