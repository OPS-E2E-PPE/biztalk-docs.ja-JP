---
title: "シングル サインオン: イベント 11070 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb669df9-710a-4792-bdd4-cca0c03fcda2
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cb0d2a868d5c8bf47cbcb5389bf2d16dadf4010a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-11070"></a>シングル サインオン: イベント 11070
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|エンタープライズ シングル サインオン|  
|製品バージョン|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|イベント ID|11070|  
|イベント ソース|ENTSSO|  
|コンポーネント|なし|  
|シンボル名|SSO_WARN_PS_MIIS_NOT_ALLOWED|  
|メッセージ テキスト|現在、この SSO サーバーでは、MIIS からの Windows パスワード変更ができないように構成されています。 'ssoconfig -allowPS MIIS yes' または SSO 管理 MMC を使用してください。%r<br /><br /> 追跡 ID: %1 %r<br /><br /> クライアント ユーザー: %2|  
  
## <a name="explanation"></a>説明  
 現在、この SSO サーバーでは、MIIS からの Windows パスワード変更ができないように構成されています。  
  
## <a name="user-action"></a>ユーザーの操作  
 MIIS から Windows パスワード変更を許可する、**サーバー スナップイン**、**パスワード同期プロパティ** タブで、 **MIIS からパスワード同期を許可します。**  
  
 詳細については、次を参照してください。[サーバー スナップインを使用する](../core/how-to-use-the-servers-snap-in.md)です。