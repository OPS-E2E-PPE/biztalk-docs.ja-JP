---
title: "シングル サインオン: イベント 11021 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 70b987aa-8097-4243-a25b-f1cc12c5bc6a
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1e246ac3d0bbab4e991b17c091567b4b59131b4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11021"></a>シングル サインオン: イベント 11021
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11021|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_INFO_EXTERNAL_TO_EXTERNAL_MAPPING_CONFLICT_ALLOWED|  
|メッセージ テキスト|外部パスワード変更によって、別の外部アカウントが変更されます。%r<br /><br /> この外部システムのアダプターは、マッピングの競合を許可するように構成されているため、これは許可されます。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> アダプター: %2 %r<br /><br /> Windows アカウント: %3 %r<br /><br /> 外部アカウント 1: %4 %r<br /><br /> 外部アカウント 2: %5|  
  
## <a name="explanation"></a>説明  
 これは、外部パスワード変更によって、別の外部アカウントが変更されることを示す情報メッセージです。  
  
## <a name="user-action"></a>ユーザーの操作  
 この変更が、管理者の理解と認可の下に行われたものであることを直ちに確認する必要があります。 そうである場合は、何もする必要はありません。 そうでなかった場合は、この変更がどこで行われたのかを調べ、システム内の安全な場所であることを確認してください。