---
title: "シングル サインオン: イベント 10605 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4c9812b4-43bc-43c4-be8f-6f57c432bda6
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e7d0fb4befaacd8734f866f2c11c7446d4e5854
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10605"></a>シングル サインオン: イベント 10605
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10605|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_ERROR_DTC_IMPORT|  
|メッセージ テキスト|DTC トランザクションをインポートできませんでした。 MSDTC がリモート操作用に正しく構成されていることを確認してください。 Details.%r のマニュアルを参照してください。<br /><br /> エラー コード: %1|  
  
## <a name="explanation"></a>説明  
 Microsoft 分散トランザクション コーディネーター (MSDTC) に問題があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 MSDTC の問題に関するヘルプを参照するには、次を参照してください。 [MSDTC の問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)です。