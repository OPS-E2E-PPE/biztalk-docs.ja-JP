---
title: シングル サインオン:イベント 10762 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 516e120d-e72b-4f40-9a81-9131ea247dd0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b26f196e2431f0229ac28b9d8f2718b551a58b1c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396652"
---
# <a name="single-sign-on-event-10762"></a>シングル サインオン:イベント 10762
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                   エンタープライズ シングル サインオン                                                    |
| 製品バージョン |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    イベント ID     |                                                             10762                                                              |
|  イベント ソース   |                                                             ENTSSO                                                             |
|    コンポーネント    |                                                              なし                                                               |
|  シンボル名  |                                                     ENTSSO_E_WRONG_THREAD                                                      |
|  メッセージ テキスト   | SSO クライアント コンポーネントは間違ったスレッドで呼び出されました。 トランザクションがあるため、現在のスレッドにロックします。 |
  
## <a name="explanation"></a>説明  
 コンポーネントはできるトランザクションがあるない場合、マルチ スレッドにのみ。 このコンポーネントでは、スレッドにロックされているため、トランザクションがあります。  
  
## <a name="user-action"></a>ユーザーの操作  
 呼び出さない SSO クライアント コンポーネント複数のスレッドでトランザクションを使用する場合、アプリケーションを構成します。