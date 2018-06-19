---
title: 複数コンピューター環境のシナリオで SSO を構成する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 45bfa58c1fc11a76109f56938b8e1b43790935f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248754"
---
# <a name="how-to-configure-sso-in-a-multicomputer-scenario"></a>複数コンピューター環境のシナリオで SSO を構成する方法
このセクションでは、3 台のコンピュータが存在するシナリオで、エンタープライズ シングル サインオン (SSO) を構成する手順について説明します。  
  
 次のシナリオでは、コンピュータ A がマスタ シークレット サーバー、コンピュータ B がシングル サインオン サーバーです。コンピュータ C には SSO データベースが保持されています。 コンピュータ B は、ランタイム サーバー、管理サーバー (SSO の管理サブサービスにより、SSO データベースを管理するために使用されるサーバー)、またはマッピング サーバー (SSO の管理サブサービスおよびクライアント サブサービスにより、マッピングを管理するために使用されるサーバー) として機能します。  
  
 環境内の SSO サーバーの台数を増やす場合は、コンピュータ B を構成する手順に従ってください。新しい SSO サーバーは、既存の SSO データベースを参照します。マスタ シークレット サーバーにすることはできません。  
  
> [!NOTE]
>  マスタ シークレット サーバーは、シングル サインオン サーバーおよび SSO データベースとは別のコンピュータで構成することをお勧めします。  
  
### <a name="to-configure-the-master-secret-server-and-create-the-sso-database-on-computer-a"></a>コンピュータ A でマスタ シークレット サーバーを構成して SSO データベースを作成するには  
  
1.  BizTalk Server のカスタム インストールを実行し、エンタープライズ シングル サインオンのマスタ シークレット サーバー コンポーネントのみをインストールします。  
  
2.  構成ウィザードを実行し、マスタ シークレット サーバーで SSO を構成します。 **構成についての質問**するオプションを選択 ページで、**新しい SSO システムを作成する**です。  
  
3.  **Windows アカウント** ページで、SSO サービスのサービス アカウントの資格情報を指定します。 このアカウントは、SSO 管理者グループのメンバである必要があります。  
  
4.  **データベース構成** ページで、SQL Server (コンピュータ C) の場所と SSO データベース (SSODB) の名前を指定します。  
  
5.  マスタ シークレットをバックアップするオプションを指定します。  
  
6.  構成を完了します。  
  
### <a name="to-configure-the-sso-server-on-computer-b"></a>コンピュータ B で SSO サーバーを構成するには  
  
1.  コンピュータ B にエンタープライズ シングル サインオンをインストールします。  
  
    > [!NOTE]
    >  このコンピュータは、BizTalk Server コンピュータか Host Integration Server コンピュータ、Web サーバー、または SSO のみのサーバー (SSO ランタイム コンポーネント) にすることができます。  
  
2.  構成ウィザードを実行して、SSO を構成します。 **構成についての質問**するオプションを選択 ページで、**既存の SSO システムに参加**です。  
  
3.  **Windows アカウント** ページで、SSO サービスのサービス アカウントの資格情報を指定します。 このアカウントは、SSO 管理者グループのメンバである必要があります。  
  
4.  **データベース構成** ページで、SQL Server (コンピュータ C) の場所と SSO データベース (SSODB) の名前をポイントします。  
  
## <a name="see-also"></a>参照  
 [マスター シークレット サーバーをクラスター化する方法](../core/how-to-cluster-the-master-secret-server1.md)   
 [SSO のインストール](../core/installing-sso.md)