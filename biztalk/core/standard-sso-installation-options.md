---
title: 標準 SSO インストール オプション |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, SSO
- SSO, installing
ms.assetid: 59aeb503-f369-4145-8a3c-ab60e9ed31a8
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 61cbba3615048b8028f5daebcadd8a649afb0f16
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392993"
---
# <a name="standard-sso-installation-options"></a>標準 SSO インストール オプション
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] シングル サインオン シナリオを有効にする資格情報を安全に格納するためのエンタープライズ シングル サインオン (SSO) 機能を活用します。  
  
 BizTalk Server では、アダプターのカスタム構成データを安全に格納するのに SSO も使用します。 これを行うには、BizTalk Server ランタイムと管理の機能は、依存特徴として SSO をインストールします。 BizTalk Server の既定のインストールには、エンタープライズ SSO がインストールされます。  
  
> [!NOTE]
>  エンタープライズ シングル サインオン (サーバー コンポーネント) のインストール時に、構成を実行する必要があります。 SSO システムを設定する最初の手順では、マスター シークレット サーバーを構成します。 スタンドアロンのマスター シークレット サーバーを設定することをお勧めします。 これは、BizTalk Server のセットアップでカスタム機能ツリーからエンタープライズ シングル サインオンのみ選択して実行できます。  
>   
>  お勧め、実行しているコンピューターでエンタープライズ シングル サインオンを実行している時刻の同期サービス。 これにより、コンピューターの時刻は、適切に機能する SSO のチケット発行サービスに必要なシステムの残りの部分との同期。  
  
 **インストール オプションの一覧**:実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップ プログラム。 選択**カスタム インストール**、次の一覧から適切なオプションを選択します。  
  
- **エンタープライズ シングル サインオンの管理**マッピングおよびエンタープライズ シングル サインオン サービスへの接続の管理とクライアント ツールです。  
  
- **エンタープライズ シングル サインオン マスター シークレット サーバー** SSO システムでは、マスター シークレット サーバーとして機能します。 これは、SSO システムを展開する必要があるは、最初のサーバーと SSO データベースを作成できます。  
  
  プログラム追加と削除ユーティリティを使用して、セットアップ後に、次を追加することもできます。  
  
- **サーバー ランタイム**コア サービスでシングル サインオンを有効にして、店舗/アクセスの構成データに安全にします。  
  
- **エンタープライズ シングル サインオンの管理**マッピングおよびエンタープライズ シングル サインオン サービスへの接続の管理とクライアント ツールです。  
  
- **パスワード同期 でのエンタープライズのシングル サインオン サービス**エンタープライズ SSO システムでパスワード同期機能を有効にするサービス。 これらのサービスは、Microsoft パスワード変更通知サービスと統合することもできます。 \Platform\SSO\Setup.exe を起動、パスワード同期を選択する BizTalk Server パッケージからエンタープライズ SSO のパスワード同期機能をインストールできますコア エンタープライズ シングル サインオン サービスをインストールした後機能です。  
  
- **ソフトウェア開発キット**プログラミングとリファレンス情報。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [SSO 管理コンポーネントをインストールする方法](../core/how-to-install-the-sso-administration-component.md)  
  
-   [SSO クライアント ユーティリティをインストールする方法](../core/how-to-install-the-sso-client-utility.md)