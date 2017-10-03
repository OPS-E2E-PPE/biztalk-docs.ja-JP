---
title: "SSO の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d729633717d709a83c10e9b50c55791029902010
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-sso"></a>SSO を構成します。
コマンド ライン ユーティリティ、UI ツール、または COM インターフェイスか Microsoft .NET インターフェイスを使用して、エンタープライズ シングル サインオンを構成できます。  
  
## <a name="sso-command-line-utilities"></a>SSO コマンド ライン ユーティリティ  
 次の 3 つの異なるコマンド ライン ユーティリティを使用して、エンタープライズ シングル サインオンの作業を実行します。  
  
 **SSOConfig です。** SSO 管理者は、SSO データベースを構成し、マスタ シークレットを管理できます。  
  
> [!NOTE]
>  構成ウィザードで SSO データベースおよびマスタ シークレット サーバーを作成します。  
  
 **SSOManage です。** SSO 管理者、SSO 関連管理者、およびアプリケーション管理者は、追加する SSO データベースの更新、アプリケーションの削除と管理、ユーザー マッピングの管理、および関連アプリケーションのユーザー用の資格情報の設定を行えます。 一部の操作をできるのは、SSO 管理者のみ、または SSO 管理者と SSO 関連管理者のみです。 アプリケーション管理者が実行できるすべての操作は、SSO 管理者および SSO 関連管理者も実行できます。  
  
 **SSOClient です。** シングル サインオン ユーザーは、固有のユーザー マッピングを管理し、資格証明を設定できます。  
  
 SSO アカウントの詳細については、次を参照してください。 [SSO ユーザー グループ](../core/sso-user-groups.md)です。  
  
## <a name="sso-ui-tools"></a>SSO UI ツール  
 **エンタープライズ SSO MMC スナップイン。** SSO 管理者、SSO 関連管理者、およびアプリケーション管理者は、SSO データベースの更新、アプリケーションの追加、削除、管理、ユーザー マッピングの管理、および関連アプリケーションのユーザー用の資格情報の設定を行うことができます。 一部の操作は、SSO 管理者のみ、または SSO 管理者と SSO 関連管理者のみが実行できます。 アプリケーション管理者が実行できるすべての操作は、SSO 管理者および SSO 関連管理者でも実行できます。  
  
 **SSO クライアント ユーティリティ。** エンド ユーザーは、UI ツールを使用して、固有のマッピングを管理し、資格証明を設定できます。  
  
## <a name="sso-com-and-net-interfaces"></a>SSO の COM インターフェイスおよび .NET インターフェイス  
 エンタープライズ シングル サインオンでは、カスタム コンポーネントの作成、および SSO システムの管理を容易にするスクリプトの作成をプログラムから行える、COM および .NET のインターフェイスを提供します。  
  
## <a name="see-also"></a>参照  
 [SSO コンポーネント](../core/sso-components.md)