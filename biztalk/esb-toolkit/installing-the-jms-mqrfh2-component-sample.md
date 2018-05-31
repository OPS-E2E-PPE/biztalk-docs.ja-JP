---
title: JMS MQRFH2 コンポーネント サンプルのインストール |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a5bd855-512f-40a4-8038-ae9b847b1097
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b522d986524c77a53cf5a847f749a9ce41e2c50
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294250"
---
# <a name="installing-the-jms-mqrfh2-component-sample"></a><span data-ttu-id="5668c-102">JMS MQRFH2 コンポーネント サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5668c-102">Installing the JMS MQRFH2 Component Sample</span></span>
<span data-ttu-id="5668c-103">このサンプルを使用する、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]次をインストールすることも必要があります。</span><span class="sxs-lookup"><span data-stu-id="5668c-103">To use this sample with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)], you must also install the following:</span></span>  
  
-   <span data-ttu-id="5668c-104">IBM WebSphere MQ 5.3 (CSD12) の WebSphere MQ 6.x または WebSphere MQ 7.0</span><span class="sxs-lookup"><span data-stu-id="5668c-104">IBM WebSphere MQ 5.3 (with CSD12), WebSphere MQ 6.x or WebSphere MQ 7.0</span></span>  
  
-   <span data-ttu-id="5668c-105">IBM"RfhUtil"JMS テスト キューとメッセージを取得するためのユーティリティ</span><span class="sxs-lookup"><span data-stu-id="5668c-105">The IBM "RfhUtil" JMS test utility for queuing and retrieving messages</span></span>  
  
 <span data-ttu-id="5668c-106">JMS MQRFH2 コンポーネント サンプルには、Microsoft BizTalk Server のインストール フォルダーとグローバル アセンブリ キャッシュに存在する対応するスキーマの PipelineComponents フォルダー内に存在する JMS MQRFH2 コンポーネントが必要です。</span><span class="sxs-lookup"><span data-stu-id="5668c-106">The JMS MQRFH2 Component sample requires the JMS MQRFH2 component to reside in the PipelineComponents folder of your Microsoft BizTalk Server installation folder and the corresponding schemas to reside in the global assembly cache.</span></span> <span data-ttu-id="5668c-107">インストール、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]コアは自動的にコピーして、適切な場所にアセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5668c-107">Installing the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automatically copies and installs the assemblies to the correct locations.</span></span> <span data-ttu-id="5668c-108">ただし、必要な場合、これらのタスクを手動で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="5668c-108">However, if required, you can manually perform these tasks.</span></span>  
  
 <span data-ttu-id="5668c-109">**JMS MQRFH2 コンポーネントとスキーマを手動でインストールするには**</span><span class="sxs-lookup"><span data-stu-id="5668c-109">**To manually install the JMS MQRFH2 component and schemas**</span></span>  
  
1.  <span data-ttu-id="5668c-110">Microsoft.Practices.ESB.JMS.PipelineComponents.dll アセンブリを BizTalk Server のインストール フォルダーの PipelineComponents フォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="5668c-110">Copy the assembly Microsoft.Practices.ESB.JMS.PipelineComponents.dll to the PipelineComponents folder of your BizTalk Server installation folder.</span></span>  
  
2.  <span data-ttu-id="5668c-111">.NET Framework 構成ツールを使用して、グローバル アセンブリ キャッシュに Microsoft.Practices.ESB.JMS.Schemas.Property.dll セクションにある、管理ツールのスキーマ アセンブリを追加、**開始**メニュー。</span><span class="sxs-lookup"><span data-stu-id="5668c-111">Add the schema assembly Microsoft.Practices.ESB.JMS.Schemas.Property.dll to the global assembly cache using the .NET Framework Configuration Tool located in the Administrative Tools section of the **Start** menu.</span></span>  
  
 <span data-ttu-id="5668c-112">このセクションでは、GlobalBank.JMS BizTalk アプリケーションに JMS MQRFH2 サンプルをインストールするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5668c-112">This section describes the process for installing the JMS MQRFH2 sample into the GlobalBank.JMS BizTalk application.</span></span> <span data-ttu-id="5668c-113">このサンプルをインストールする前に」の説明に従って、ESB Toolkit のコアをインストールする必要があります[BizTalk ESB Toolkit のコアをインストールする](http://go.microsoft.com/fwlink/?LinkId=187612)([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612))。</span><span class="sxs-lookup"><span data-stu-id="5668c-113">Before you install this sample, you must install the ESB Toolkit Core as described in [Installing the BizTalk ESB Toolkit Core](http://go.microsoft.com/fwlink/?LinkId=187612) ([http://go.microsoft.com/fwlink/?LinkId=187612](http://go.microsoft.com/fwlink/?LinkId=187612)).</span></span>  
  
 <span data-ttu-id="5668c-114">ソリューションのプロジェクトから、JMS MQRFH2 コンポーネント サンプルをインストールまたはに付属する Windows インストーラー ファイルを使用することができます、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="5668c-114">You can install the JMS MQRFH2 Component sample from the solution project or use the Windows Installer file included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="5668c-115">このセクションのトピックは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5668c-115">This section contains the following topics:</span></span>  
  
-   [<span data-ttu-id="5668c-116">インストール スクリプトを使用して、JMS MQRFH2 サンプルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5668c-116">Install the JMS MQRFH2 Sample Using the Install Scripts</span></span>](../esb-toolkit/install-the-jms-mqrfh2-sample-using-the-install-scripts.md)  
  
-   [<span data-ttu-id="5668c-117">アセンブリおよび JMS MQRFH2 コンポーネント サンプルがインストールされているアイテム</span><span class="sxs-lookup"><span data-stu-id="5668c-117">Assemblies and Artifacts Installed by the JMS MQRFH2 Component Sample</span></span>](../esb-toolkit/assemblies-and-artifacts-installed-by-the-jms-mqrfh2-component-sample.md)  
  
-   [<span data-ttu-id="5668c-118">JMS MQRFH2 サンプルのインストールをテストします。</span><span class="sxs-lookup"><span data-stu-id="5668c-118">Test the JMS MQRFH2 Sample Installation</span></span>](../esb-toolkit/test-the-jms-mqrfh2-sample-installation.md)