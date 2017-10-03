---
title: "手順 2: が作成および展開サンプル X12 スキーマ |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5862168-6621-40ab-8c97-3f317530d34e
caps.latest.revision: "31"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe4f937af910ceef1ed461e25ea3c62cad5cbc29
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-create-and-deploy-the-sample-x12-schema"></a><span data-ttu-id="0bed5-102">手順 2: が作成および展開サンプル X12 スキーマ</span><span class="sxs-lookup"><span data-stu-id="0bed5-102">Step 2: Create and Deploy the Sample X12 Schema</span></span>
<span data-ttu-id="0bed5-103">![手順 11 の 2](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")</span><span class="sxs-lookup"><span data-stu-id="0bed5-103">![Step 2 of 11](../core/media/tut-step2-of-11.gif "Tut_Step2_of_11")</span></span>  
  
 <span data-ttu-id="0bed5-104">このステップでは、AS2 トランスポートを経由した受信 EDI X12 インターチェンジを処理するために必要な、サンプル EDI X12 スキーマを提供するプロジェクトをビルドし、展開します。</span><span class="sxs-lookup"><span data-stu-id="0bed5-104">In this step, you build and deploy the project that provides a sample EDI X12 schema that is required to process the incoming EDI X12 interchange transported over AS2.</span></span> <span data-ttu-id="0bed5-105">このチュートリアルでは、スキーマ X12_00401_864.xsd を使用します。</span><span class="sxs-lookup"><span data-stu-id="0bed5-105">For this tutorial, that schema is X12_00401_864.xsd.</span></span> <span data-ttu-id="0bed5-106">AS2 チュートリアルに付属のプロジェクトを変更する必要はありません。実行する必要があるのはビルドだけです。</span><span class="sxs-lookup"><span data-stu-id="0bed5-106">You do not need to change the project that is shipped with the AS2 tutorial; you just need to build it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0bed5-107">このチュートリアルで使用するスキーマ ファイル X12_00401_864.xsd は、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas フォルダー内にあります。</span><span class="sxs-lookup"><span data-stu-id="0bed5-107">The schema file X12_00401_864.xsd that this tutorial uses is stored in the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas.</span></span> <span data-ttu-id="0bed5-108">このスキーマ ファイルは、このステップでビルドと展開を行う対象の Schemas プロジェクトに既に追加されています。</span><span class="sxs-lookup"><span data-stu-id="0bed5-108">It has already been added to the Schemas project that you will build and deploy in this step.</span></span> <span data-ttu-id="0bed5-109">このスキーマは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI フォルダーにある MicrosoftEdiXsdTemplates.exe を実行してコンピューターにダウンロードされる X12_00401_864.xsd ファイルとは異なります。</span><span class="sxs-lookup"><span data-stu-id="0bed5-109">This schema is different from the X12_00401_864.xsd file downloaded onto your computer by executing MicrosoftEdiXsdTemplates.exe in the folder [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI.</span></span> <span data-ttu-id="0bed5-110">このチュートリアルを実行するには、Schemas.btproj に追加されている X12_00401_864.xsd ファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bed5-110">The tutorial will only work if you use the X12_00401_864.xsd file that has been added to Schemas.btproj.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0bed5-111">前提条件</span><span class="sxs-lookup"><span data-stu-id="0bed5-111">Prerequisites</span></span>  
 <span data-ttu-id="0bed5-112">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bed5-112">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-create-and-deploy-the-sample-x12-schema"></a><span data-ttu-id="0bed5-113">サンプル X12 スキーマを作成して展開するには</span><span class="sxs-lookup"><span data-stu-id="0bed5-113">To create and deploy the sample X12 schema</span></span>  
  
1.  <span data-ttu-id="0bed5-114">開始**Microsoft Visual Studio**を管理者として。</span><span class="sxs-lookup"><span data-stu-id="0bed5-114">Start **Microsoft Visual Studio** as an administrator.</span></span>  
  
2.  <span data-ttu-id="0bed5-115">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] で、ソリューション [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.sln を開きます。</span><span class="sxs-lookup"><span data-stu-id="0bed5-115">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], open the solution [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\AS2 Tutorial\Schemas\Schemas.sln.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0bed5-116">このトピックは、EDI スキーマ、パイプライン、およびオーケストレーションを含む BizTalk EDI アプリケーションに別のアプリケーションから参照を既に追加していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0bed5-116">This topic assumes that you have already added a reference from your application to the BizTalk EDI Application, which contains EDI schemas, pipelines, and orchestrations.</span></span> <span data-ttu-id="0bed5-117">いない場合を参照してください。[を BizTalk Server EDI アプリケーションへの参照を追加する方法](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782)です。</span><span class="sxs-lookup"><span data-stu-id="0bed5-117">If not, see [How to Add a Reference to the BizTalk Server EDI Application](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).</span></span>  
  
3.  <span data-ttu-id="0bed5-118">Schemas プロジェクトを右クリックし、をクリックして**プロパティ**です。</span><span class="sxs-lookup"><span data-stu-id="0bed5-118">Right-click the Schemas project, and then click **Properties**.</span></span> <span data-ttu-id="0bed5-119">クリックして、**署名**プロジェクト デザイナーのタブです。</span><span class="sxs-lookup"><span data-stu-id="0bed5-119">Click the **Signing** tab in project designer.</span></span> <span data-ttu-id="0bed5-120">チェック、**アセンブリに署名** チェック ボックスの**強力なキー名ファイルを選択して**を選択**\<新規作成 ...> >**入力と`Schemas.snk`です。</span><span class="sxs-lookup"><span data-stu-id="0bed5-120">Check the **Sign the Assembly** checkbox, for **Choose a strong key name file**, select **\<New…>** and enter `Schemas.snk`.</span></span> <span data-ttu-id="0bed5-121">クリア**キーファイルをパスワードで保護する**順にクリック**OK**です。</span><span class="sxs-lookup"><span data-stu-id="0bed5-121">Clear **Protect my key file with a password** and then click **OK**.</span></span> <span data-ttu-id="0bed5-122">プロジェクトのプロパティのダイアログ ボックスを閉じ、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="0bed5-122">Close the project properties dialog and save the changes.</span></span>  
  
4.  <span data-ttu-id="0bed5-123">Schemas.btproj をビルドおよび展開します。</span><span class="sxs-lookup"><span data-stu-id="0bed5-123">Build and deploy Schemas.btproj.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0bed5-124">次の手順</span><span class="sxs-lookup"><span data-stu-id="0bed5-124">Next Steps</span></span>  
 <span data-ttu-id="0bed5-125">説明に従って、組織 (Contoso) のパーティとビジネス プロファイルを構成する[手順 3: 組織のパーティとビジネス プロファイルを構成する](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)です。</span><span class="sxs-lookup"><span data-stu-id="0bed5-125">You configure a party and business profile for your organization (Contoso), as described in [Step 3: Configure a Party and Business Profile for Your Organization](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bed5-126">参照</span><span class="sxs-lookup"><span data-stu-id="0bed5-126">See Also</span></span>  
 [<span data-ttu-id="0bed5-127">EDI ドキュメント スキーマ</span><span class="sxs-lookup"><span data-stu-id="0bed5-127">EDI Document Schemas</span></span>](../core/edi-document-schemas.md)