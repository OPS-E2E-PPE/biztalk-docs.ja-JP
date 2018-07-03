---
title: 'シングル サインオン: イベント 10762 |Microsoft Docs'
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
ms.openlocfilehash: 905c59062f8f4af397872f3f7d4434a67b19842e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996011"
---
# <a name="single-sign-on-event-10762"></a>シングル サインオン: イベント 10762
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                |
|-----------------|--------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                                   エンタープライズ シングル サインオン                                                    |
| 製品バージョン |                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                   |
|    イベント ID     |                                                             10762                                                              |
|  イベント ソース   |                                                             ENTSSO                                                             |
|    コンポーネント    |                                                              なし                                                               |
|  シンボル名  |                                                     ENTSSO_E_WRONG_THREAD                                                      |
|  メッセージ テキスト   | SSO クライアント コンポーネントが不適切なスレッドで呼び出されました。 コンポーネントにトランザクションがあるため、現在コンポーネントはスレッドにロックされています。 |
  
## <a name="explanation"></a>説明  
 コンポーネントは、トランザクションがない場合にのみマルチスレッド化することができます。 このコンポーネントにはトランザクションがあるので、スレッドにロックされています。  
  
## <a name="user-action"></a>ユーザーの操作  
 トランザクションを使用しているときには複数のスレッドで SSO クライアント コンポーネントを呼び出さないようにアプリケーションを構成します。