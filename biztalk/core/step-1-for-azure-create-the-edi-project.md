---
title: '手順 1 (Azure 用): EDI プロジェクトを作成する |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9d353129-04f0-456b-b371-b346959f5155
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec854bc6edecb59e9cb721c71dafa09c3e0bc2dc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018132"
---
# <a name="step-1-for-azure-create-the-edi-project"></a><span data-ttu-id="37627-102">手順 1 (Azure 用): EDI プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="37627-102">Step 1 (For Azure): Create the EDI Project</span></span>
<span data-ttu-id="37627-103">このセクションでは、Contoso が、[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] の 2012 年 4 月リリース版を使用して EDI プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="37627-103">In this section, Contoso creates an EDI project using the [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] April 2012 release.</span></span> <span data-ttu-id="37627-104">プロジェクトの一部として、Contoso は以下の項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="37627-104">As part of the project, Contoso adds the following:</span></span>  
  
- <span data-ttu-id="37627-105">内部の販売注文スキーマ (**ECommerceSalesOrder.xsd**) を X12 840 EDI 販売注文スキーマに変換されます。</span><span class="sxs-lookup"><span data-stu-id="37627-105">An internal sales order schema (**ECommerceSalesOrder.xsd**) to which the X12 840 EDI sales order schema will be transformed.</span></span> <span data-ttu-id="37627-106">Contoso は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] で受信した後のメッセージの処理に内部スキーマを使用します。</span><span class="sxs-lookup"><span data-stu-id="37627-106">Contoso uses the internal schema to process the message after it is received into [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span></span>  
  
- <span data-ttu-id="37627-107">変換 (**EDI840TOSALESORDER します。TRFM**) 840 販売注文スキーマを X12 に変換する、 **ECommerceSalesOrder**スキーマ。</span><span class="sxs-lookup"><span data-stu-id="37627-107">A transform (**EDI840TOSALESORDER.TRFM**) to convert the X12 840 sales order schema to the **ECommerceSalesOrder** schema.</span></span>  
  
  <span data-ttu-id="37627-108">Contoso は、[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)] で Azure BizTalk ポータルのアグリーメントを作成するときにこれらのアイテムを使用します。</span><span class="sxs-lookup"><span data-stu-id="37627-108">Contoso uses these artifacts while creating an agreement in the Azure BizTalk portal in [!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)].</span></span>  
  
### <a name="to-create-edi-project"></a><span data-ttu-id="37627-109">EDI プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="37627-109">To create EDI project</span></span>  
  
1.  <span data-ttu-id="37627-110">Visual Studio を開き、**ファイル** メニューをポイント**新規**、 をクリックし、**プロジェクト**します。</span><span class="sxs-lookup"><span data-stu-id="37627-110">Open Visual Studio, from the **File** menu point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="37627-111">**新しいプロジェクト** ダイアログ ボックスから、**インストールされたテンプレート**を選択します**Service Bus**します。</span><span class="sxs-lookup"><span data-stu-id="37627-111">In the **New Project** dialog box, from the **Installed Templates**, select **Service Bus**.</span></span> <span data-ttu-id="37627-112">プロジェクトの名前と、プロジェクトの場所を指定し、クリックして**OK**します。</span><span class="sxs-lookup"><span data-stu-id="37627-112">Specify a project name and a location for the project, and then click **OK**.</span></span>  
  
##  <a name="BKMK_CreateSchema"></a> <span data-ttu-id="37627-113">EDI プロジェクト内のスキーマを作成するには</span><span class="sxs-lookup"><span data-stu-id="37627-113">To create a schema within the EDI project</span></span>  
  
1.  <span data-ttu-id="37627-114">ソリューション エクスプ ローラーで、先ほど作成したプロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="37627-114">From the Solution Explorer, right-click the project name you just created, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="37627-115">**新しい項目の追加** ダイアログ ボックスから、**インストールされたテンプレート**を選択します**スキーマ**、として、スキーマの名前を指定**ECommerceSalesOrder.xsd**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="37627-115">In the **Add New Item** dialog box, from the **Installed Templates**, select **Schema**, specify the name of the schema as **ECommerceSalesOrder.xsd**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="37627-116">スキーマを編集して以下のように構築します。</span><span class="sxs-lookup"><span data-stu-id="37627-116">Edit and build the schema to resemble the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <xs:schema xmlns="http://ECommerceSalesOrder.Inbound" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://ECommerceSalesOrder.Inbound" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
      <xs:element name="SalesOrder">  
        <xs:complexType>  
          <xs:sequence>  
            <xs:element name="CompanyCode" type="xs:string" />  
            <xs:element name="PartID" type="xs:int" />  
            <xs:element name="Quantity" type="xs:int" />  
            <xs:element name="AskPrice" type="xs:decimal" />  
            <xs:element name="RequestShipmentDate" type="xs:date" />  
            <xs:element name="Address">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Line1" type="xs:string" />  
                  <xs:element name="Line2" type="xs:string" />  
                  <xs:element name="City" type="xs:string" />  
                  <xs:element name="State" type="xs:string" />  
                  <xs:element name="Country" type="xs:string" />  
                  <xs:element name="Zipcode" type="xs:int" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Contact">  
              <xs:complexType>  
                <xs:sequence>  
                  <xs:element name="Firstname" type="xs:string" />  
                  <xs:element name="Lastname" type="xs:string" />  
                </xs:sequence>  
              </xs:complexType>  
            </xs:element>  
            <xs:element name="Comments" type="xs:string" />  
            <xs:element name="DateNow" type="xs:date" />  
          </xs:sequence>  
        </xs:complexType>  
      </xs:element>  
    </xs:schema>  
    ```  
  
     <span data-ttu-id="37627-117">スキーマの構築にはスキーマ エディターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="37627-117">You can use the Schema Editor to build this schema.</span></span> <span data-ttu-id="37627-118">詳細については、次を参照してください。 [BizTalk エディターを使用して](../core/using-biztalk-editor.md)します。</span><span class="sxs-lookup"><span data-stu-id="37627-118">For more information, see [Using BizTalk Editor](../core/using-biztalk-editor.md).</span></span>  
  
4.  <span data-ttu-id="37627-119">スキーマを保存します。</span><span class="sxs-lookup"><span data-stu-id="37627-119">Save the schema.</span></span>  
  
##  <a name="BKMK_CreateTrfm"></a> <span data-ttu-id="37627-120">EDI プロジェクト内の変換を作成するには</span><span class="sxs-lookup"><span data-stu-id="37627-120">To create a transform within the EDI project</span></span>  
  
1.  <span data-ttu-id="37627-121">ソリューション エクスプ ローラーで、先ほど作成したプロジェクト名を右クリックして**追加**、 をクリックし、**新しい項目の**します。</span><span class="sxs-lookup"><span data-stu-id="37627-121">From the Solution Explorer, right-click the project name you just created, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="37627-122">**新しい項目の追加** ダイアログ ボックスから、**インストールされたテンプレート**を選択します**マップ**、として、スキーマの名前を指定**Edi840ToSalesOrder.trfm**、 をクリックし、**追加**します。</span><span class="sxs-lookup"><span data-stu-id="37627-122">In the **Add New Item** dialog box, from the **Installed Templates**, select **Map**, specify the name of the schema as **Edi840ToSalesOrder.trfm**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="37627-123">マップでは、送信元スキーマの選択**X12_00401_840.xsd**します。</span><span class="sxs-lookup"><span data-stu-id="37627-123">In the map, for the source schema select **X12_00401_840.xsd**.</span></span> <span data-ttu-id="37627-124">これは、EDI 販売注文の標準 X12 スキーマです。</span><span class="sxs-lookup"><span data-stu-id="37627-124">This is the standard X12 schema for an EDI sales order.</span></span> <span data-ttu-id="37627-125">作成した EDI プロジェクトに既にこのスキーマが追加されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="37627-125">You must have already added this schema to the EDI project you created.</span></span> <span data-ttu-id="37627-126">これは、およびその他の X12 をダウンロードできますからスキーマ[ http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)します。</span><span class="sxs-lookup"><span data-stu-id="37627-126">You can download this, and other X12 schemas from [http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057).</span></span> <span data-ttu-id="37627-127">スキーマの一部は、X12、 **MicrosoftEdiXSDTemplates.zip**ダウンロード場所からパッケージを使用可能です。</span><span class="sxs-lookup"><span data-stu-id="37627-127">The X12 schemas are part of the **MicrosoftEdiXSDTemplates.zip** package available from the download location.</span></span>  
  
4.  <span data-ttu-id="37627-128">送信先スキーマでは、選択**ECommerceSalesOrder.xsd**します。</span><span class="sxs-lookup"><span data-stu-id="37627-128">For the destination schema, select **ECommerceSalesOrder.xsd**.</span></span> <span data-ttu-id="37627-129">このスキーマは、このトピックで既に作成済みです。</span><span class="sxs-lookup"><span data-stu-id="37627-129">You created this schema earlier in this topic.</span></span>  
  
5.  <span data-ttu-id="37627-130">送信元と送信先のスキーマ内の関連するノードを接続してマップを作成します。</span><span class="sxs-lookup"><span data-stu-id="37627-130">Create the map by connecting the relevant nodes in the source and target schemas.</span></span>  
  
6.  <span data-ttu-id="37627-131">マップを保存します。</span><span class="sxs-lookup"><span data-stu-id="37627-131">Save the map.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37627-132">参照</span><span class="sxs-lookup"><span data-stu-id="37627-132">See Also</span></span>  
 [<span data-ttu-id="37627-133">チュートリアル 4: BizTalk Server 2013 を使用してハイブリッド アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="37627-133">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)