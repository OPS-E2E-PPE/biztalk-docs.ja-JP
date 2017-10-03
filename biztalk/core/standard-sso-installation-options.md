---
title: "標準 SSO インストール オプション |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, installing
ms.assetid: 59aeb503-f369-4145-8a3c-ab60e9ed31a8
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26441ca5d63ebdb4cba807173f7e7068ff846bdf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="standard-sso-installation-options"></a>標準 SSO インストール オプション
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、資格情報を安全に格納するためにエンタープライズ シングル サインオン (SSO) 機能を利用して、シングル サインオン シナリオを実現します。  
  
 また、BizTalk Server では、アダプタのカスタム構成データを安全に格納する場合にも SSO を使用します。 これを行うために、BizTalk Server のランタイム機能および管理機能から SSO が依存機能としてインストールされます。 BizTalk Server の既定のインストールでは、エンタープライズ SSO がインストールされます。  
  
> [!NOTE]
>  エンタープライズ シングル サインオン (サーバー コンポーネント) をインストールするときに、構成を行う必要があります。 SSO システムをセットアップするには、まず、マスタ シークレット サーバーを構成します。 スタンドアロンのマスタ シークレット サーバーをセットアップすることをお勧めします。 このセットアップを行うには、BizTalk Server のセットアップ時にカスタム機能ツリーからエンタープライズ シングル サインオンを選択するだけです。  
>   
>  また、エンタープライズ シングル サインオンを実行しているコンピュータでは、時刻同期サービスを実行しておくこともお勧めします。 時刻同期サービスを実行すると、コンピュータの時刻と残りのシステムとの同期が維持されます。これは、SSO チケット サービスを正常に機能させるために必要です。  
  
 **インストール オプションの一覧**: 実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップ プログラム。 選択**カスタム インストール**、次の一覧から適切なオプションを選択します。  
  
-   **エンタープライズ シングル サインオンの管理**マッピングおよびエンタープライズ シングル サインオン サービスに接続するための管理およびクライアント ツールです。  
  
-   **エンタープライズ シングル サインオン マスター シークレット サーバー** SSO システムでマスター シークレット サーバーとして機能します。 これは、SSO システムで展開する必要のある、最初のサーバーです。このサーバーで、SSO データベースを作成できます。  
  
 セットアップ後、[プログラムの追加と削除] ユーティリティを使用して次の項目を追加することもできます。  
  
-   **サーバー ランタイム**コア サービスでのシングル サインオンを有効にして、ストア/アクセスの構成データに安全にします。  
  
-   **エンタープライズ シングル サインオンの管理**マッピングおよびエンタープライズ シングル サインオン サービスに接続するための管理およびクライアント ツールです。  
  
-   **パスワード同期 でのエンタープライズのシングル サインオン サービス**Services エンタープライズ SSO システムでパスワード同期機能を有効にします。 これらのサービスは、Microsoft パスワード変更通知サービスとも統合されます。 中核となるエンタープライズ シングル サインオン サービスをインストールした後、\Platform\SSO\Setup.exe を起動してパスワード同期機能を選択すると、BizTalk Server パッケージからエンタープライズ SSO のパスワード同期機能をインストールできます。  
  
-   **ソフトウェア開発キット**プログラミングとリファレンス情報。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SSO 管理コンポーネントをインストールする方法](../core/how-to-install-the-sso-administration-component.md)  
  
-   [SSO クライアント ユーティリティをインストールする方法](../core/how-to-install-the-sso-client-utility.md)