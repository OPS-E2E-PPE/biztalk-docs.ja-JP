---
title: シングル サインオン インターフェイスの動作を変更する方法 |Microsoft Docs
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
ms.openlocfilehash: 729b5faee2e6adff6e43a987b1defcb90450eb13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387068"
---
# <a name="how-to-change-the-behavior-of-a-single-sign-on-interface"></a>シングル サインオン インターフェイスの動作を変更する方法
エンタープライズ シングル サインオン (SSO) オブジェクト モデル内のオブジェクトの多くは、IPropertyBag インターフェイスは、指定したオブジェクトの動作を変更することができますを公開します。 SSO オブジェクトの QueryInterface を呼び出す場合は、IPropertyBag インターフェイスを取得しを使用して、現在のオブジェクトの動作を変更します。  

### <a name="to-change-the-behavior-for-a-specified-sso-interface"></a>指定した SSO インターフェイスの動作を変更するには  

1.  指定したインターフェイスの QueryInterface を使用して、IPropertyBag インスタンスを取得します。  

2.  IPropertyBag.Write を使用すると、プロパティ、型、およびインターフェイスの値を設定できます。  

     次の表では、IPropertyBag の propname パラメーターと ptrVar パラメーターの有効な値について説明します。  

|propname パラメーター|型|ptrValue|使用できます。|  
|--------------|----------|--------------|---------------|  
|CurrentSSOServer|VT_BSTR|情報を送信するサーバーの名前|All|  
|トランザクション|VT_UNKNOWN<br /><br /> VT_EMPTY|DTC ITransaction ポインター、またはスコープをクリアする NULL。|ISSOConfigStore::SetConfigInfo<br />ISSOConfigStore::GetConfigInfo <br />ISSOConfigStore::DeleteConfigInfo<br /><br /> ISSOAdmin::CreateApplication<br />ISSOAdmin::DeleteApplication <br />ISSOAdmin::UpdateApplication<br />ISSOAdmin::CreateFieldInfo<br /><br /> ISSOMapper::GetFieldInfo|  
|AppFilterFlags|VT_I4<br /><br /> VT_UI4|どのようなアプリケーションをフィルター処理を制御するフラグを設定します。|ISSOMapper::GetApplications<br /><br /> ISSOMapper2::GetApplications2|  
|可|VT_I4<br /><br /> VT_UI4|どのようなアプリケーションをフィルター処理を制御するフラグ マスク。|ISSOMapper::GetApplications<br /><br /> ISSOMapper2::GetApplications2|  
|AsyncCall|VT_BOOL|非同期 RPC; を使用して呼び出す場合は true同期 RPC を使用する場合は false。|ISSOConfigOM::GetServerStatus<br /><br /> ISSOAdmin::GetGlobalInfo|  

- **CurrentSSOServer**: SSO 情報を送信する先のサーバーは、次のように決定するには、標準の動作。  

  1. 現在のユーザーのレジストリを検索します。 サーバー名は、コマンド ライン ツールまたは GUI を使用して現在のユーザーに対して設定できます。  

  2. すべてのユーザーのレジストリを検索します。 サーバー名は、コマンド ライン ツールまたは GUI を使用してすべてのユーザーに対して設定できます。  

  3. SSO サーバー名がレジストリに存在しない場合は、現在のコンピューターを使用します。  

     指定したサーバーへの CurrentSSOServer の設定には、指定されたインターフェイスの前のプロセスよりも優先されます。 CurrentSSOServer を設定した後は、指定されたサーバーに、インターフェイス上のすべての後続のメソッド呼び出しが送信されます。  

- **トランザクション**: DTC トランザクションを SSO によって、操作を実行するスコープ オブジェクト モデルを指定します。 DTC ITransaction ポインターを渡す必要があります`ptrValue`、または"null"を現在のトランザクション スコープをオフにします。  

- **AppFilterFlags/AppFilterMask**: アプリケーションの種類を制御 ISSOMapper.GetApplications および ISSOMapper2.GetApplications から返されます。 アプリケーション フラグがフィルター フラグおよびフィルター フラグ マスクで指定されたフラグに一致する場合は、これらが返されます。 アプリケーションのフィルター処理を実行する方法の 1 つは、いずれに可を設定して、AppFilterFlags を次の 1 つ以上に設定するには。  

   SSO_APP_TYPE_INDIVIDUAL  

   SSO_APP_TYPE_GROUP  

   SSO_APP_TYPE_CONFIG_STORE  

   SSO_APP_TYPE_HOST_GROUP  

   SSO_APP_TYPE_PS_ADAPTER  

   SSO_APP_TYPE_PS_GROUP_ADAPTER  

- **AsyncCall**: かどうか true の場合、SSO を実行して非同期リモート プロシージャ コール (RPC) を使用して、メソッド。 メソッドでは、実行中の E_PENDING を返します。 その他の戻り値は、メソッドが完了したことを示します。 AsyncCall では、メソッドの完了をポーリングすることもできます。
