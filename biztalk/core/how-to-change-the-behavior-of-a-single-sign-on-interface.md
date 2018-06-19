---
title: シングル サインオン インターフェイスの動作を変更する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f4a4946a-e345-4c7e-835d-a3f7f72ebaca
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a4bedc387b879d5ddf21197e3dec4470f2e9b36
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247858"
---
# <a name="how-to-change-the-behavior-of-a-single-sign-on-interface"></a>シングル サインオン インターフェイスの動作を変更する方法
エンタープライズ シングル サインオン (SSO) オブジェクト モデルのオブジェクトの多くは、IPropertyBag インターフェイスを公開するので、指定したオブジェクトの動作を変更することができます。 SSO オブジェクトの QueryInterface を呼び出すと、IPropertyBag インターフェイスを取得し、それを使用して現在のオブジェクトの動作を変更できます。  
  
### <a name="to-change-the-behavior-for-a-specified-sso-interface"></a>指定した SSO インターフェイスの動作を変更するには  
  
1.  指定したインターフェイスの QueryInterface を使用して、IPropertyBag インスタンスを取得します。  
  
2.  IPropertyBag.Write を使用して、インターフェイスのプロパティ、種類、および値を設定します。  
  
     次の表に、IPropertyBag の propName パラメーターと ptrVar パラメーターの有効な値を示します。  
  
|propName|型|ptrValue|以下で使用可能|  
|--------------|----------|--------------|---------------|  
|CurrentSSOServer|VT_BSTR|情報の送信先のサーバーの名前|すべて|  
|トランザクション|VT_UNKNOWN<br /><br /> VT_EMPTY|DTC ITransaction ポインター、またはスコープをクリアする NULL|ISSOConfigStore::SetConfigInfo<br />ISSOConfigStore::GetConfigInfo <br />ISSOConfigStore::DeleteConfigInfo<br /><br /> ISSOAdmin::CreateApplication<br />ISSOAdmin::DeleteApplication <br />ISSOAdmin::UpdateApplication<br />ISSOAdmin::CreateFieldInfo<br /><br /> ISSOMapper::GetFieldInfo|  
|AppFilterFlags|VT_I4<br /><br /> VT_UI4|どのアプリケーションをフィルター処理するかを制御するフラグ|ISSOMapper::GetApplications<br /><br /> ISSOMapper2::GetApplications2|  
|AppFilterFlagsMask|VT_I4<br /><br /> VT_UI4|どのアプリケーションをフィルター処理するかを制御するフラグ マスク|ISSOMapper::GetApplications<br /><br /> ISSOMapper2::GetApplications2|  
|AsyncCall|VT_BOOL|非同期 RPC を使用して呼び出す場合は true、同期 RPC を使用する場合は false|ISSOConfigOM::GetServerStatus<br /><br /> ISSOAdmin::GetGlobalInfo|  
  
-   **CurrentSSOServer**: SSO 情報を送信するサーバーは、次のように決定するには、標準の動作。  
  
    1.  現在のユーザーのレジストリを検索します。 コマンド ライン ツールまたは GUI を使用して、サーバー名が現在のユーザーに設定されます。  
  
    2.  すべてのユーザーのレジストリを検索します。 コマンド ライン ツールまたは GUI を使用して、サーバー名がすべてのユーザーに設定されます。  
  
    3.  SSO サーバー名がレジストリで見つからなかった場合は、現在のコンピューターを使用します。  
  
     指定したサーバーへの CurrentSSOServer の設定は、指定したインターフェイスの上記の処理よりも優先されます。 CurrentSSOServer を設定すると、インターフェイスでの後続のメソッド呼び出しは、すべて指定したサーバーへ送信されます。  
  
-   **トランザクション**: DTC トランザクションを SSO によって、操作を実行するスコープにオブジェクト モデルを指定します。 `ptrValue` に、DTC ITransaction ポインター、または現在のトランザクション スコープをクリアする "null" を渡す必要があります。  
  
-   **Appfilterflags/appfiltermask**: コントロールの種類のアプリケーションがどうなる ISSOMapper.GetApplications および ISSOMapper2.GetApplications から返されます。 アプリケーション フラグがフィルター フラグおよびフィルター フラグ マスクで指定されているフラグと一致すると、そのフラグが返されます。 アプリケーションのフィルター処理を実行する 1 つの方法は、AppFilterFlagsMask を SSO_FLAG_APP_FILTER_BY_TYPE に設定して、AppFilterFlags を次のフラグのいずれか (複数可) に設定することです。  
  
     SSO_APP_TYPE_INDIVIDUAL  
  
     SSO_APP_TYPE_GROUP  
  
     SSO_APP_TYPE_CONFIG_STORE  
  
     SSO_APP_TYPE_HOST_GROUP  
  
     SSO_APP_TYPE_PS_ADAPTER  
  
     SSO_APP_TYPE_PS_GROUP_ADAPTER  
  
-   **AsyncCall**: かどうかは true、し、SSO が実行されます非同期リモート プロシージャ コール (RPC) を使用して、メソッドです。 実行中、メソッドは E_PENDING を返します。 その他の戻り値は、メソッドが完了したことを示します。 AsyncCall では、メソッドをポーリングして完了したかどうかを確認することもできます。