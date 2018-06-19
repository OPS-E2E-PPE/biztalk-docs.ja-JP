---
title: 'シングル サインオン: イベント 10762 |Microsoft ドキュメント'
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
ms.openlocfilehash: 487fbeb0f077950605432861a9118eacd93f2c89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276586"
---
# <a name="single-sign-on-event-10762"></a>シングル サインオン: イベント 10762
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10762|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_WRONG_THREAD|  
|メッセージ テキスト|SSO クライアント コンポーネントが不適切なスレッドで呼び出されました。 コンポーネントにトランザクションがあるため、現在コンポーネントはスレッドにロックされています。|  
  
## <a name="explanation"></a>説明  
 コンポーネントは、トランザクションがない場合にのみマルチスレッド化することができます。 このコンポーネントにはトランザクションがあるので、スレッドにロックされています。  
  
## <a name="user-action"></a>ユーザーの操作  
 トランザクションを使用しているときには複数のスレッドで SSO クライアント コンポーネントを呼び出さないようにアプリケーションを構成します。