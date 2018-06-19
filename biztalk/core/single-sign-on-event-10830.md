---
title: 'シングル サインオン: イベント 10830 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fd149be1-0a4f-4d39-9b0e-35202dc140cb
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d5944fe4e0af6c5e0484fd344d08ef839901e38
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276426"
---
# <a name="single-sign-on-event-10830"></a>シングル サインオン: イベント 10830
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10830|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_PSADMIN_ADAPTER_SAME_COMPUTER|  
|メッセージ テキスト|指定されたアダプターは、グループ アダプターと同じコンピューター上に存在する必要があります。|  
  
## <a name="explanation"></a>説明  
 グループ アダプター内の各アダプターは、グループ アダプターと同じコンピューター名で構成されている必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 詳細については、次を参照してください[パスワード同期。](../core/password-synchronization2.md)  
  
 のインスタンスにアクセスするたびに SQL Server ログインを指定する必要はありません。