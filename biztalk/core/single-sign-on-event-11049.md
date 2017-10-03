---
title: "シングル サインオン: イベント 11049 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 031ec1a6-4b2b-46b2-9dbb-5525d758651f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45ac6095950e02e7e73ab287b180bc22d88b4191
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11049"></a>シングル サインオン: イベント 11049
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11049|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_ERROR_DTC_FAILED|  
|メッセージ テキスト|MSDTC を取得できませんでした。 SSO を正しく機能させるには MSDTC が必要です。|  
  
## <a name="explanation"></a>説明  
 ENTSSO システムが、Microsoft 分散トランザクション コーディネーター (MSDTC) に接続できませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 MSDTC が現在動作しているかどうかを確認します。  
  
 MSDTC の問題に関するヘルプを参照するには、次を参照してください。 [MSDTC の問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)です。