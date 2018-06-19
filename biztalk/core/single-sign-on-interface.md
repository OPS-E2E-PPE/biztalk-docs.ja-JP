---
title: シングル サインオン インターフェイス |Microsoft ドキュメント
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
ms.openlocfilehash: ee479a29a424228b31bc3fcd5752f8da7cc3ce28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276794"
---
# <a name="single-sign-on-interface"></a>シングル サインオン インターフェイス

## <a name="interfaces"></a>インターフェイス
次の表に、シングル サインオン インターフェイスを構成する COM インターフェイスおよび .NET Framework インターフェイスを示します。  
  
|[.NET]|COM (COM)|Description|  
|----------|---------|-----------------|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOAdmin|ISSOAdmin インターフェイス (COM)|SSO アプリケーションを作成、更新、削除します。 その他の管理機能も実行します。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOConfigStore|ISSOConfigStore インターフェイス (COM)|SSO 構成ストアの情報を取得および設定します。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup1|ISSOLookup1 インターフェイス (COM)|現在のユーザーの指定されたアプリケーションの外部資格情報を参照できます。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOLookup2|ISSOLookup2 インターフェイス (COM)|上記と同様。ただし、指定された外部ユーザーの Windows 資格情報も参照できます。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapper|ISSOMapper インターフェイス (COM)|指定されたアプリケーションの現在のユーザーの外部資格情報を設定できます。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOMapping|ISSOMapping インターフェイス (COM)|ユーザーと関連アプリケーションとのマッピングを作成および管理します。|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOTicket|ISSOTicket インターフェイス (COM)|適切なセキュリティ情報を含むチケットを作成します。 作成されたチケットは、適切なメッセージと共にアプリケーションから送信されます。|  


## <a name="password-sync-helper"></a>パスワード同期ヘルパー  
 また、Host Integration Server は、パスワード同期ヘルパー (PS ヘルパー) コンポーネントをサポートします。 パスワード同期コンポーネントのデザイン時に、PS ヘルパーを使用できます。 次の表に、PS ヘルパーによって公開される COM インターフェイスおよび .NET Framework インターフェイスを示します。  
  
|[.NET]|COM (COM)|Description|  
|----------|---------|-----------------|  
|Microsoft.EnterpriseSingleSignOn.Interop.ISSOPSWrapper|ISSONotification インターフェイス (COM)|Windows 以外のオペレーティング システムに対するパスワード変更を処理します。|  
||SExternalAccount 構造 (COM)|外部アカウントを示します。|  
||SPasswordChange 構造 (COM)|パスワード変更を示します。|  
||SPasswordChangeComplete 構造 (COM)|パスワード変更の完了を示します。|  
||SStatus 構造 (COM)|エラーまたはイベントを示します。|  
||SAdapterInGroup 構造 (COM)|特定のグループのアダプターを示します。|  
||SAdapter 構造 (COM)|特定のアダプターを示します。|

## <a name="see-also"></a>参照
SSO の COM オブジェクトを参照してください[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]です。 