---
title: 複数コンピューターのシナリオで SSO を構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, SSO
- SSO database, clustering
- clustering, Master Secret server
- SSO, configuring
- configuring, Master Secret server
- Master Secret server, clustering
- clustering, SSO database
- Master Secret server, configuring
- SSO, multiple computers
ms.assetid: 4511a03d-96f2-45f0-9891-e8b3e253499c
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09bdaefef80a0a3e975c9d63e1844475ae698c4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386211"
---
# <a name="how-to-configure-sso-in-a-multicomputer-scenario"></a>複数コンピューターのシナリオで SSO を構成する方法
このセクションでは、3 台のコンピューターのシナリオでは、エンタープライズ シングル サインオン (SSO) を構成するための手順を説明します。  
  
 次のシナリオでは、コンピュータ A がマスタ シークレット サーバー、コンピュータ B が、シングル サインオン サーバーおよびコンピューター C は、SSO データベースを保持します。 コンピューター B の管理サーバーとしてのランタイム サーバーとして動作することができます (SSO の管理サブサービスを使用して、このサーバーの SSO データベースを管理するため)、またはマッピング サーバー (管理およびクライアント サブサービスの SSO のマッピングの管理にこのサーバーを使用)。  
  
 環境内に SSO サーバーを追加する場合はコンピューター B を構成する手順に従ってください。新しい SSO サーバーは、既存の SSO データベースがポイントして、マスター シークレット サーバーにすることはできません。  
  
> [!NOTE]
>  シングル サインオン サーバーおよび SSO データベースから別のコンピューターでは、マスター シークレット サーバーを構成することをお勧めします。  
  
### <a name="to-configure-the-master-secret-server-and-create-the-sso-database-on-computer-a"></a>マスター シークレット サーバーを構成し、コンピューター A で、SSO データベースを作成するには  
  
1.  BizTalk Server のカスタム インストールを実行し、エンタープライズ シングル サインオン マスター シークレット サーバー コンポーネントのみをインストールします。  
  
2.  SSO マスター シークレット サーバーを構成する構成ウィザードを実行します。 **構成についての質問**するオプションを選択 ページで、**新しい SSO システムを作成する**します。  
  
3.  **Windows アカウント**ページで、SSO サービスのサービス アカウントの資格情報を指定します。 これにより、SSO 管理者グループのメンバーがある必要があります。  
  
4.  **データベース構成** ページで、SQL Server (コンピュータ C) の場所と SSO データベース (SSODB) の名前を指定します。  
  
5.  マスター シークレットをバックアップするオプションを指定します。  
  
6.  構成を完了します。  
  
### <a name="to-configure-the-sso-server-on-computer-b"></a>コンピューター B で SSO サーバーを構成するには  
  
1.  コンピューター B にエンタープライズ シングル サインオンをインストールします。  
  
    > [!NOTE]
    >  BizTalk Server または Host Integration Server コンピューター、Web サーバー、または SSO のみサーバー (SSO ランタイム コンポーネント) を指定できます。  
  
2.  SSO を構成する構成ウィザードを実行します。 **構成についての質問**するオプションを選択 ページで、**既存の SSO システムに参加**します。  
  
3.  **Windows アカウント**ページで、SSO サービスのサービス アカウントの資格情報を指定します。 これにより、SSO 管理者グループのメンバーがある必要があります。  
  
4.  **データベース構成** ページで、SQL Server (コンピュータ C) の場所と SSO データベース (SSODB) の名前をポイントします。  
  
## <a name="see-also"></a>参照  
 [マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)   
 [SSO のインストール](../core/installing-sso.md)