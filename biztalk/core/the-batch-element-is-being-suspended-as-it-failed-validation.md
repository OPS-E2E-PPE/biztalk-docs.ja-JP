---
title: 検証に失敗したため、バッチ要素が中断されています |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea5e19e8-4592-40f4-bffe-85ab27653fd5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0198f6091b1d7dd6e4ade10260e8f8ffe5b59765
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65298981"
---
# <a name="the-batch-element-is-being-suspended-as-it-failed-validation"></a>検証に失敗したため、バッチ要素が中断されています
## <a name="details"></a>詳細  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  製品名   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| 製品バージョン |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    イベント ID     |                                           -                                            |
|  イベント ソース   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI |
|    コンポーネント    |                                    バッチ処理エンジン                                     |
|  シンボル名  |                                 BatchElementSuspended                                  |
|  メッセージ テキスト   |    検証に失敗したため、バッチ要素を中断されています。 エラーです。 {0}    |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、バッチ処理オーケストレーションが、トランザクション セットをバッチ インターチェンジをトランザクション セットには、バッチ処理オーケストレーションによって行われる検証が失敗したために追加できなかったことを示します。 検証に失敗したトランザクションが設定されていないインターチェンジが生成されます。 バッチ処理オーケストレーションは、EDI を設定します。"True"に BatchElementValidationFailure コンテキスト プロパティです。 BatchSuspend オーケストレーションはそのコンテキスト プロパティに基づいてメッセージを取得するには、エラー情報を送信しは中断されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するを示す、トランザクション セットの送信者にどのようなエラーが発生したエラー メッセージに記載されています。 検証が失敗する原因となった問題を解決して、トランザクション セットを再送信し、送信者に依頼します。