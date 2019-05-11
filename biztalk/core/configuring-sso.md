---
title: SSO の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, command line utilities
- configuring, SSO
- SSO, interfaces
- SSOConfig [SSO]
- SSO, configuring
- SSOClient [SSO]
- SSO, tools
- SSOManage [SSO]
ms.assetid: 6f755735-9b48-4771-beec-ced844f3d532
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19825ec6f420b8ec3e30f5dead09ad1d901503f8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355197"
---
# <a name="configuring-sso"></a>SSO を構成します。
コマンド ライン ユーティリティ、UI ツール、または COM コンポーネントまたは Microsoft .NET インターフェイスを使用して、エンタープライズ シングル サインオン構成することができます。  
  
## <a name="sso-command-line-utilities"></a>SSO コマンド ライン ユーティリティ  
 次の 3 つの異なるコマンド ライン ユーティリティを使用して、エンタープライズ シングル サインオンのタスクを実行します。  
  
 **SSOConfig します。** SSO 管理者は SSO データベースを構成して、マスター シークレットを管理できます。  
  
> [!NOTE]
>  構成ウィザードでは、SSO データベースとマスター シークレット サーバーを作成します。  
  
 **SSOManage します。** SSO 管理者、SSO 関連管理者、およびアプリケーション管理者、SSO データベースを更新する、追加、削除、アプリケーションの管理と、ユーザーのマッピングの管理と、関連会社の資格情報をアプリケーションのユーザー設定を有効にします。 一部の操作は、SSO 管理者によってのみ実行できるまたは、だけで、SSO 管理者と SSO 関連管理者。 アプリケーション管理者が実行できるすべての操作は、SSO 管理者と SSO 関連管理者でも実行できます。  
  
 **SSOClient します。** シングル サインオンをユーザーが自分のユーザー マッピングを管理し、自分の資格情報を設定できます。  
  
 SSO アカウントの詳細については、次を参照してください。 [SSO ユーザー グループ](../core/sso-user-groups.md)します。  
  
## <a name="sso-ui-tools"></a>SSO UI ツール  
 **エンタープライズ SSO MMC スナップイン。** SSO 管理者、SSO 関連管理者、およびアプリケーション管理者と、SSO データベースの更新を追加、削除し、アプリケーションの管理、ユーザーのマッピングの管理、アプリケーションのユーザーに、関連会社の資格情報を設定できます。 だけで、SSO 管理者と SSO 関連管理者または、SSO 管理者だけがいくつかの操作を実行できます。 アプリケーション管理者が実行できるすべての操作は、SSO 管理者および SSO 関連管理者でも実行できます。  
  
 **SSO クライアント ユーティリティ。** エンドユーザーが自分のマッピングを管理し、UI ツールを使用して、資格情報を設定できます。  
  
## <a name="sso-com-and-net-interfaces"></a>SSO の COM および .NET インターフェイス  
 エンタープライズ シングル サインオンを使用するカスタム コンポーネントを作成して、SSO システムの管理に役立つスクリプトを作成する COM と .NET のプログラミング インターフェイスを提供します。  
  
## <a name="see-also"></a>参照  
 [SSO コンポーネント](../core/sso-components.md)