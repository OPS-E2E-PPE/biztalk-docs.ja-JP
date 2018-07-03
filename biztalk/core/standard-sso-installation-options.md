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
ms.openlocfilehash: a734114bb6d89c73b275e1060719c6b2cb638566
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981723"
---
# <a name="standard-sso-installation-options"></a><span data-ttu-id="4c652-102">標準 SSO インストール オプション</span><span class="sxs-lookup"><span data-stu-id="4c652-102">Standard SSO Installation Options</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4c652-103"> では、資格情報を安全に格納するためにエンタープライズ シングル サインオン (SSO) 機能を利用して、シングル サインオン シナリオを実現します。</span><span class="sxs-lookup"><span data-stu-id="4c652-103"> leverages the Enterprise Single Sign-On (SSO) capabilities for securely storing credentials to enable single sign-on scenarios.</span></span>  
  
 <span data-ttu-id="4c652-104">また、BizTalk Server では、アダプタのカスタム構成データを安全に格納する場合にも SSO を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c652-104">BizTalk Server also uses SSO to store custom configuration data of Adapters securely.</span></span> <span data-ttu-id="4c652-105">これを行うために、BizTalk Server のランタイム機能および管理機能から SSO が依存機能としてインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4c652-105">To do this, BizTalk Server runtime and administration features install SSO as a dependent feature.</span></span> <span data-ttu-id="4c652-106">BizTalk Server の既定のインストールでは、エンタープライズ SSO がインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4c652-106">The default installation of BizTalk Server installs Enterprise SSO.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c652-107">エンタープライズ シングル サインオン (サーバー コンポーネント) をインストールするときに、構成を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c652-107">When Enterprise Single Sign-on (Server component) is installed, configuration needs to be performed.</span></span> <span data-ttu-id="4c652-108">SSO システムをセットアップするには、まず、マスタ シークレット サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="4c652-108">The first step to set up an SSO System is to configure the master secret server.</span></span> <span data-ttu-id="4c652-109">スタンドアロンのマスタ シークレット サーバーをセットアップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4c652-109">It is recommended to set up a stand-alone master secret server.</span></span> <span data-ttu-id="4c652-110">このセットアップを行うには、BizTalk Server のセットアップ時にカスタム機能ツリーからエンタープライズ シングル サインオンを選択するだけです。</span><span class="sxs-lookup"><span data-stu-id="4c652-110">This can be done by only selecting Enterprise Single Sign-on from the custom feature tree in BizTalk Server setup.</span></span>  
>   
>  <span data-ttu-id="4c652-111">また、エンタープライズ シングル サインオンを実行しているコンピュータでは、時刻同期サービスを実行しておくこともお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4c652-111">We also recommend that any computer running Enterprise Single Sign-On have a time synchronization service running.</span></span> <span data-ttu-id="4c652-112">時刻同期サービスを実行すると、コンピュータの時刻と残りのシステムとの同期が維持されます。これは、SSO チケット サービスを正常に機能させるために必要です。</span><span class="sxs-lookup"><span data-stu-id="4c652-112">This keeps the computer time in sync with the rest of the system, which is necessary for SSO ticketing services to function properly.</span></span>  
  
 <span data-ttu-id="4c652-113">**インストール オプションの一覧**: 実行、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップ プログラム。</span><span class="sxs-lookup"><span data-stu-id="4c652-113">**List of installation options**: Run the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup program.</span></span> <span data-ttu-id="4c652-114">選択**カスタム インストール**、次の一覧から適切なオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4c652-114">Select **Custom Installation**, and then select the appropriate option from the following list:</span></span>  
  
- <span data-ttu-id="4c652-115">**エンタープライズ シングル サインオンの管理**マッピングおよびエンタープライズ シングル サインオン サービスへの接続の管理とクライアント ツールです。</span><span class="sxs-lookup"><span data-stu-id="4c652-115">**Enterprise Single Sign-On Administration ―** Administration and client tools for mapping and connecting to Enterprise Single Sign-On Services.</span></span>  
  
- <span data-ttu-id="4c652-116">**エンタープライズ シングル サインオン マスター シークレット サーバー** SSO システムでは、マスター シークレット サーバーとして機能します。</span><span class="sxs-lookup"><span data-stu-id="4c652-116">**Enterprise Single Sign-On Master Secret Server ―** Acts as the Master Secret Server in the SSO System.</span></span> <span data-ttu-id="4c652-117">これは、SSO システムで展開する必要のある、最初のサーバーです。このサーバーで、SSO データベースを作成できます。</span><span class="sxs-lookup"><span data-stu-id="4c652-117">This is the first server in the SSO System that needs to deployed and this allows you to create the SSO database.</span></span>  
  
  <span data-ttu-id="4c652-118">セットアップ後、[プログラムの追加と削除] ユーティリティを使用して次の項目を追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="4c652-118">You can also add the following after setup, by using the Add or Remove Programs utility:</span></span>  
  
- <span data-ttu-id="4c652-119">**サーバー ランタイム**コア サービスでシングル サインオンを有効にして、店舗/アクセスの構成データに安全にします。</span><span class="sxs-lookup"><span data-stu-id="4c652-119">**Server Runtime ―** Core services to enable single sign-on and to store/access configuration data securely.</span></span>  
  
- <span data-ttu-id="4c652-120">**エンタープライズ シングル サインオンの管理**マッピングおよびエンタープライズ シングル サインオン サービスへの接続の管理とクライアント ツールです。</span><span class="sxs-lookup"><span data-stu-id="4c652-120">**Enterprise Single Sign-On Administration ―** Administration and client tools for mapping and connecting to Enterprise Single Sign-On Services.</span></span>  
  
- <span data-ttu-id="4c652-121">**パスワード同期 でのエンタープライズのシングル サインオン サービス**エンタープライズ SSO システムでパスワード同期機能を有効にするサービス。</span><span class="sxs-lookup"><span data-stu-id="4c652-121">**Enterprise Single Sign-On Services with Password Synchronization ―** Services to enable the Password Synchronization feature in the Enterprise SSO System.</span></span> <span data-ttu-id="4c652-122">これらのサービスは、Microsoft パスワード変更通知サービスとも統合されます。</span><span class="sxs-lookup"><span data-stu-id="4c652-122">These services also integrate with the Microsoft Password Change Notification Service.</span></span> <span data-ttu-id="4c652-123">中核となるエンタープライズ シングル サインオン サービスをインストールした後、\Platform\SSO\Setup.exe を起動してパスワード同期機能を選択すると、BizTalk Server パッケージからエンタープライズ SSO のパスワード同期機能をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4c652-123">Once you have installed the core Enterprise Single Sign-On services, you can install the Password Synchronization feature of Enterprise SSO from the BizTalk Server package by launching the \Platform\SSO\Setup.exe and selecting the Password Synchronization feature.</span></span>  
  
- <span data-ttu-id="4c652-124">**ソフトウェア開発キット**プログラミングとリファレンス情報。</span><span class="sxs-lookup"><span data-stu-id="4c652-124">**Software Development Kit** Programming and Reference information.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4c652-125">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="4c652-125">In This Section</span></span>  
  
-   [<span data-ttu-id="4c652-126">SSO 管理コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="4c652-126">How to Install the SSO Administration Component</span></span>](../core/how-to-install-the-sso-administration-component.md)  
  
-   [<span data-ttu-id="4c652-127">SSO クライアント ユーティリティをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="4c652-127">How to Install the SSO Client Utility</span></span>](../core/how-to-install-the-sso-client-utility.md)