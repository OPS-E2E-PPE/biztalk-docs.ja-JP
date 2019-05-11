---
title: シングル サインオン インターフェイス |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e2e3c2d3-a7e9-4a45-965d-bfe4bf200c34
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: be71b6be0baa733748552f59067b0b3678bed4af
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65247282"
---
# <a name="single-sign-on-interface"></a>シングル サインオン インターフェイス

## <a name="interfaces"></a>インターフェイス
次の表では、シングル サインオン インターフェイスを構成する COM および .NET Framework のインターフェイスについて説明します。  
  
|[.NET]|COM (COM)|説明|  
|----------|---------|-----------------|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOAdmin|ISSOAdmin インターフェイス (COM)|作成、更新、および SSO アプリケーションを削除します。 他の管理機能を実行します。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOConfigStore|ISSOConfigStore インターフェイス (COM)|取得し、SSO 構成ストアの情報を設定します。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup1|ISSOLookup1 インターフェイス (COM)|現在のユーザーの指定したアプリケーションの外部資格情報を検索できます。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup2|ISSOLookup2 インターフェイス (COM)|上記のようにも、指定された外部ユーザーの Windows 資格情報を参照できます。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapper|ISSOMapper インターフェイス (COM)|指定されたアプリケーションの現在のユーザーの外部資格情報を設定できます。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapping|ISSOMapping インターフェイス (COM)|作成し、ユーザーと関連アプリケーションの間のマッピングを維持します。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOTicket|ISSOTicket インターフェイス (COM)|適切なセキュリティ情報を含むチケットを作成します。 このチケットはし、アプリケーションから適切なメッセージ送信されます。|  


## <a name="password-sync-helper"></a>パスワード同期ヘルパー  
 さらに、Host Integration Server では、パスワード同期ヘルパー (PS ヘルパー) コンポーネントをサポートしています。 パスワード同期コンポーネントをデザインするときに、PS ヘルパーを使用することができます。 次の表では、PS ヘルパーによって公開される COM および .NET Framework のインターフェイスについて説明します。  
  
|[.NET]|COM (COM)|説明|  
|----------|---------|-----------------|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOPSWrapper|ISSONotification インターフェイス (COM)|非 Windows オペレーティング システムとの間のパスワードの変更を処理します。|  
||SExternalAccount 構造 (COM)|外部アカウントをについて説明します。|  
||SPasswordChange 構造 (COM)|パスワードの変更について説明します。|  
||SPasswordChangeComplete 構造 (COM)|パスワードの変更の完了をについて説明します。|  
||SStatus 構造 (COM)|エラーまたはイベントについて説明します。|  
||SAdapterInGroup 構造 (COM)|特定のグループ アダプターをについて説明します。|  
||SAdapter 構造 (COM)|特定のアダプターについて説明します。|

## <a name="see-also"></a>関連項目
SSO の COM オブジェクトを参照してください。[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]します。 