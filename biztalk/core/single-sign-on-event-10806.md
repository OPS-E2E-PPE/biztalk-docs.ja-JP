---
title: "シングル サインオン: イベント 10806 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23650d6b-b6a4-4c41-96cd-476e5b0f7f63
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd3f432a408cffcbd1ccd27508550fd0888c5213
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10806"></a>シングル サインオン: イベント 10806
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|10806|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|ENTSSO_E_APP_ASSIGNED_TO_ADAPTER|  
|メッセージ テキスト|アプリケーションは、現在アダプターに割り当てられているため削除できません。|  
  
## <a name="explanation"></a>説明  
 アプリケーションがアダプターに割り当てられている場合、アプリケーションを削除できません。  
  
## <a name="user-action"></a>ユーザーの操作  
 アダプターからアプリケーションの割り当てを解除し、アプリケーションを削除します。