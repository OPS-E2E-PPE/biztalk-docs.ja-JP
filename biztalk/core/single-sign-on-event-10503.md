---
title: 'シングル サインオン: イベント 10503 |Microsoft Docs'
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
ms.openlocfilehash: b90af01551359b5caa1a5404facc9e3fece95673
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990715"
---
# <a name="single-sign-on-event-10503"></a>シングル サインオン: イベント 10503
## <a name="details"></a>詳細  

|                 |                                                               |
|-----------------|---------------------------------------------------------------|
|  製品名   |                   エンタープライズ シングル サインオン                   |
| 製品バージョン |  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]   |
|    イベント ID     |                             10503                             |
|  イベント ソース   |                            ENTSSO                             |
|    コンポーネント    |                              N\A                              |
|  シンボル名  |                SSO_ERROR_SERVICE_START_FAILED                 |
|  メッセージ テキスト   | SSO サービスを開始できませんでした。%r<br /><br /> エラー コード: %1 |

## <a name="explanation"></a>説明  
 このエラー イベントは、例外が発生したために ENTSSO サービスを開始できなかったことを示します。  

## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の操作を行います。  

- ENTSSO または他のサービスからの関連するエラーについては、システムおよびアプリケーションのイベント ログを確認します。  

  詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプの次の情報を参照してください:   

- [SSO の使用](../core/using-sso.md)
