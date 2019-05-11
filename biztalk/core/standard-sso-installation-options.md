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
# <a name="standard-sso-installation-options"></a><span data-ttu-id="5f1e7-102">標準 SSO インストール オプション</span><span class="sxs-lookup"><span data-stu-id="5f1e7-102">Standard SSO Installation Options</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="5f1e7-103">シングル サインオン シナリオを有効にする資格情報を安全に格納するためのエンタープライズ シングル サインオン (SSO) 機能を活用します。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-103">leverages the Enterprise Single Sign-On (SSO) capabilities for securely storing credentials to enable single sign-on scenarios.</span></span>  
  
 <span data-ttu-id="5f1e7-104">BizTalk Server では、アダプターのカスタム構成データを安全に格納するのに SSO も使用します。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-104">BizTalk Server also uses SSO to store custom configuration data of Adapters securely.</span></span> <span data-ttu-id="5f1e7-105">これを行うには、BizTalk Server ランタイムと管理の機能は、依存特徴として SSO をインストールします。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-105">To do this, BizTalk Server runtime and administration features install SSO as a dependent feature.</span></span> <span data-ttu-id="5f1e7-106">BizTalk Server の既定のインストールには、エンタープライズ SSO がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-106">The default installation of BizTalk Server installs Enterprise SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5f1e7-107">エンタープライズ シングル サインオン (サーバー コンポーネント) のインストール時に、構成を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-107">When Enterprise Single Sign-on (Server component) is installed, configuration needs to be performed.</span></span> <span data-ttu-id="5f1e7-108">SSO システムを設定する最初の手順では、マスター シークレット サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-108">The first step to set up an SSO System is to configure the master secret server.</span></span> <span data-ttu-id="5f1e7-109">スタンドアロンのマスター シークレット サーバーを設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-109">It is recommended to set up a stand-alone master secret server.</span></span> <span data-ttu-id="5f1e7-110">これは、BizTalk Server のセットアップでカスタム機能ツリーからエンタープライズ シングル サインオンのみ選択して実行できます。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-110">This can be done by only selecting Enterprise Single Sign-on from the custom feature tree in BizTalk Server setup.</span></span>  
>   
>  <span data-ttu-id="5f1e7-111">お勧め、実行しているコンピューターでエンタープライズ シングル サインオンを実行している時刻の同期サービス。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-111">We also recommend that any computer running Enterprise Single Sign-On have a time synchronization service running.</span></span> <span data-ttu-id="5f1e7-112">これにより、コンピューターの時刻は、適切に機能する SSO のチケット発行サービスに必要なシステムの残りの部分との同期。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-112">This keeps the computer time in sync with the rest of the system, which is necessary for SSO ticketing services to function properly.</span></span>  
  
 <span data-ttu-id="5f1e7-113">**インストール オプションの一覧**:実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップ プログラム。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-113">**List of installation options**: Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup program.</span></span> <span data-ttu-id="5f1e7-114">選択**カスタム インストール**、次の一覧から適切なオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-114">Select **Custom Installation**, and then select the appropriate option from the following list:</span></span>  
  
- <span data-ttu-id="5f1e7-115">**エンタープライズ シングル サインオンの管理**マッピングおよびエンタープライズ シングル サインオン サービスへの接続の管理とクライアント ツールです。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-115">**Enterprise Single Sign-On Administration ―** Administration and client tools for mapping and connecting to Enterprise Single Sign-On Services.</span></span>  
  
- <span data-ttu-id="5f1e7-116">**エンタープライズ シングル サインオン マスター シークレット サーバー** SSO システムでは、マスター シークレット サーバーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-116">**Enterprise Single Sign-On Master Secret Server ―** Acts as the Master Secret Server in the SSO System.</span></span> <span data-ttu-id="5f1e7-117">これは、SSO システムを展開する必要があるは、最初のサーバーと SSO データベースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-117">This is the first server in the SSO System that needs to deployed and this allows you to create the SSO database.</span></span>  
  
  <span data-ttu-id="5f1e7-118">プログラム追加と削除ユーティリティを使用して、セットアップ後に、次を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-118">You can also add the following after setup, by using the Add or Remove Programs utility:</span></span>  
  
- <span data-ttu-id="5f1e7-119">**サーバー ランタイム**コア サービスでシングル サインオンを有効にして、店舗/アクセスの構成データに安全にします。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-119">**Server Runtime ―** Core services to enable single sign-on and to store/access configuration data securely.</span></span>  
  
- <span data-ttu-id="5f1e7-120">**エンタープライズ シングル サインオンの管理**マッピングおよびエンタープライズ シングル サインオン サービスへの接続の管理とクライアント ツールです。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-120">**Enterprise Single Sign-On Administration ―** Administration and client tools for mapping and connecting to Enterprise Single Sign-On Services.</span></span>  
  
- <span data-ttu-id="5f1e7-121">**パスワード同期 でのエンタープライズのシングル サインオン サービス**エンタープライズ SSO システムでパスワード同期機能を有効にするサービス。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-121">**Enterprise Single Sign-On Services with Password Synchronization ―** Services to enable the Password Synchronization feature in the Enterprise SSO System.</span></span> <span data-ttu-id="5f1e7-122">これらのサービスは、Microsoft パスワード変更通知サービスと統合することもできます。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-122">These services also integrate with the Microsoft Password Change Notification Service.</span></span> <span data-ttu-id="5f1e7-123">\Platform\SSO\Setup.exe を起動、パスワード同期を選択する BizTalk Server パッケージからエンタープライズ SSO のパスワード同期機能をインストールできますコア エンタープライズ シングル サインオン サービスをインストールした後機能です。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-123">Once you have installed the core Enterprise Single Sign-On services, you can install the Password Synchronization feature of Enterprise SSO from the BizTalk Server package by launching the \Platform\SSO\Setup.exe and selecting the Password Synchronization feature.</span></span>  
  
- <span data-ttu-id="5f1e7-124">**ソフトウェア開発キット**プログラミングとリファレンス情報。</span><span class="sxs-lookup"><span data-stu-id="5f1e7-124">**Software Development Kit** Programming and Reference information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5f1e7-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="5f1e7-125">In This Section</span></span>  
  
-   [<span data-ttu-id="5f1e7-126">SSO 管理コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="5f1e7-126">How to Install the SSO Administration Component</span></span>](../core/how-to-install-the-sso-administration-component.md)  
  
-   [<span data-ttu-id="5f1e7-127">SSO クライアント ユーティリティをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="5f1e7-127">How to Install the SSO Client Utility</span></span>](../core/how-to-install-the-sso-client-utility.md)