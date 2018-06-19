---
title: 'シングル サインオン: イベント 10757 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24765a25-560b-4391-9839-a325894c679f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5887694e8fd307c0738fc7596c52354925bfbc7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277506"
---
# <a name="single-sign-on-event-10757"></a>シングル サインオン: イベント 10757
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10757|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_NO_MAPPING|  
|メッセージ テキスト|マッピングが存在しません。 構成ストア アプリケーションの場合は、構成情報が設定されていません。|  
  
## <a name="explanation"></a>説明  
 これが単独アプリケーションまたはグループ アプリケーションである場合は、マッピングは存在しません。  
  
 これが構成ストア アプリケーションである場合は、構成データが設定されていません。 このような状況は、SSO データベースが再初期化されているが、BizTalk 管理データベースは再初期化されていない場合、またはその逆の場合に発生します。  
  
## <a name="user-action"></a>ユーザーの操作  
 これが単独アプリケーションまたはグループ アプリケーションである場合は、目的のマッピングを作成します。 詳細については、次を参照してください。[ユーザー マッピングを作成する方法](../core/how-to-create-user-mappings.md)です。