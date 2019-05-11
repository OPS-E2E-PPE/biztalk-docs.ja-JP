---
title: シングル サインオン:イベント 10503 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 04292ae8-8daf-4f5a-837e-fe5dfcd02b10
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72b82421d4c70833f085b8e95c75c60cb1944545
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243447"
---
# <a name="single-sign-on-event-10503"></a>シングル サインオン:イベント 10503
## <a name="details"></a>詳細  

|                 |                                                               |
|-----------------|---------------------------------------------------------------|
|  製品名   |                   エンタープライズ シングル サインオン                   |
| 製品バージョン |  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    イベント ID     |                             10503                             |
|  イベント ソース   |                            ENTSSO                             |
|    コンポーネント    |                              該当なし                              |
|  シンボル名  |                SSO_ERROR_SERVICE_START_FAILED                 |
|  メッセージ テキスト   | Start.%r SSO サービスが失敗しました<br /><br /> エラー コード: %1 |

## <a name="explanation"></a>説明  
 このエラー イベントは、例外により、ENTSSO サービスを開始できなかったことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- ENTSSO または他のサービスから関連するエラーのアプリケーションとシステムの両方のイベント ログを確認します。  

  詳細については、の次のリソースを参照してください。[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプ。  

- [SSO の使用](../core/using-sso.md)
