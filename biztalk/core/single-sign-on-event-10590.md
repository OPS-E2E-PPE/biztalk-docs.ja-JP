---
title: 'シングル サインオン: イベント 10590 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd8c3804-5c84-403f-881b-e4b101c2323a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 542e597c56f1049133670c91f233d82f5f431b78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271866"
---
# <a name="single-sign-on-event-10590"></a>シングル サインオン: イベント 10590
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10590|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_ERROR_OUT_OF_SERVICE|  
|メッセージ テキスト|エンタープライズ シングル サインオンは、オフラインに移行しています。|  
  
## <a name="explanation"></a>説明  
 通常、ENTSSO システムは 30 秒ごとに ENTSSO データベースの更新を検査します。 指定されている時間 (通常は 5 分) の間データベースが使用できない場合、システム自体がオフラインになります。 この状態では、システムは資格情報の要求に応答しません。 一部のオフラインおよび管理アクティビティはこの状態でも使用できます。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーは、ENTSSO データベースがオフラインであることを示します。 直ちに調査する必要があります。