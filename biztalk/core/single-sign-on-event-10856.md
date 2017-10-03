---
title: "シングル サインオン: イベント 10856 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 10c06a86-e402-4adc-abbe-5ded923d626a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6be0f098929e0419378de9eaebdf0ca00f5eb421
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10856"></a>シングル サインオン: イベント 10856
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10856|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_MAPPING_CREATE_RESTRICTED|  
|メッセージ テキスト|アプリケーション ユーザーは、このアプリケーションのマッピングを作成できません。|  
  
## <a name="explanation"></a>説明  
 このアプリケーションは、Application Users グループのメンバーにマッピングの作成を許可するように構成されていませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 十分な特権を持つユーザーにこのようなマッピングの作成を依頼する必要があります。