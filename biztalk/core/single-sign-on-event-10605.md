---
title: シングル サインオン:イベント 10605 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4c9812b4-43bc-43c4-be8f-6f57c432bda6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 181191572cd433ebcd6ab2356a1cb0455c6a4c09
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397776"
---
# <a name="single-sign-on-event-10605"></a>シングル サインオン:イベント 10605
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                                       |
|-----------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                                       エンタープライズ シングル サインオン                                                                       |
| 製品バージョン |                                                      [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                       |
|    イベント ID     |                                                                                 10605                                                                                 |
|  イベント ソース   |                                                                                ENTSSO                                                                                 |
|    コンポーネント    |                                                                                  なし                                                                                  |
|  シンボル名  |                                                                         SSO_ERROR_DTC_IMPORT                                                                          |
|  メッセージ テキスト   | DTC トランザクションをインポートできませんでした。 MSDTC がリモート操作用に正しく構成されていることを確認してください。 Details.%r のドキュメントを参照してください。<br /><br /> エラー コード: %1 |
  
## <a name="explanation"></a>説明  
 Microsoft 分散トランザクション コーディネーター (MSDTC) に問題があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 MSDTC の問題に関するヘルプは、次を参照してください。 [MSDTC を使用した問題のトラブルシューティング](../core/troubleshooting-problems-with-msdtc.md)します。