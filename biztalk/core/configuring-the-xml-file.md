---
title: "XML ファイルの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 52851901-8374-412f-9c29-83845d8d4861
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d791de9b6fe90ebb850874026e8d52e49732f32
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-the-xml-file"></a><span data-ttu-id="2c63c-102">XML ファイルの構成</span><span class="sxs-lookup"><span data-stu-id="2c63c-102">Configuring the XML File</span></span>
<span data-ttu-id="2c63c-103">エンタープライズ シングル サインオン (SSO) をインストールすると、ENTSSO.xml という XML ファイルが Extensions ディレクトリにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2c63c-103">When you install Enterprise Single Sign-On (SSO), an XML file named ENTSSO.xml is installed in your Extensions directory.</span></span> <span data-ttu-id="2c63c-104">このファイルを編集することにより、ENTSSO 管理エージェント (MA) のすべてのインスタンスに適用される構成を定義できます。</span><span class="sxs-lookup"><span data-stu-id="2c63c-104">By editing the file, you define the configuration for all instances of the ENTSSO Management Agent (MA).</span></span>  
  
 <span data-ttu-id="2c63c-105">このファイルは、次のような内容で構成されています。</span><span class="sxs-lookup"><span data-stu-id="2c63c-105">The file is similar to the following:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<sso>  
  
  <SourceMA name="RACFMA1" objectType="person" attribute="uid"/>  
  <SourceMA name="ACF2" objectType="person" attribute="uid"/>  
  
  <ENTSSOMA name ="ENTSSOMA1" adma="ADMA1" deleteAll="true">  
    <Application name="AppForRACF1A" sourceMA="RACFMA1" create="true" delete="true"/>  
    <Application name="AppForRACF1B" sourceMA="RACFMA1" create="true" delete="false"/>  
  </ENTSSOMA>  
  
  <ENTSSOMA name ="ENTSSOMA2" adma="ADMA1" deleteAll="true">  
    <Application name="AppForACF2" sourceMA="ACF2"/>  
  </ENTSSOMA>  
  
</sso>  
```  
  
## <a name="xml-elements-and-attributes"></a><span data-ttu-id="2c63c-106">XML 要素と XML 属性</span><span class="sxs-lookup"><span data-stu-id="2c63c-106">XML Elements and Attributes</span></span>  
 <span data-ttu-id="2c63c-107">次の一覧は、この XML ファイルで定義する要素と属性について説明したものです。</span><span class="sxs-lookup"><span data-stu-id="2c63c-107">The following list describes the elements and attributes that you define in the XML file.</span></span> <span data-ttu-id="2c63c-108">このファイル内のすべての要素名と属性名では、小文字と大文字が区別されます。</span><span class="sxs-lookup"><span data-stu-id="2c63c-108">Note that all element and attribute names in this file are case sensitive.</span></span>  
  
 <span data-ttu-id="2c63c-109">**要素: ENTSSO** -単一の ENTSSO MA インスタンスの構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-109">**Element: ENTSSO** - Defines the configuration of a single ENTSSO MA instance.</span></span> <span data-ttu-id="2c63c-110">複数の ENTSSO 要素は使用できません。</span><span class="sxs-lookup"><span data-stu-id="2c63c-110">Multiple ENTSSO elements are allowed.</span></span>  
  
 <span data-ttu-id="2c63c-111">**属性: 名前**- ENTSSO 管理エージェントのインスタンスの名前を定義し、Microsoft Identity Integration Server (MIIS) の ENTSSO 管理エージェント インスタンスの名前に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c63c-111">**Attribute: name** - Defines the instance name of the ENTSSO Management Agent, and must match the name of the ENTSSO Management Agent instance in Microsoft Identity Integration Server (MIIS).</span></span>  
  
 <span data-ttu-id="2c63c-112">**属性: adma** -この ENTSSO 管理エージェント インスタンスによって使用される Active Directory 管理エージェントのインスタンスの名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-112">**Attribute: adma** - Defines the instance name of the Active Directory Management Agent that will be used by this ENTSSO Management Agent instance.</span></span> <span data-ttu-id="2c63c-113">Active Directory 管理エージェントでは、マッピング用の Windows ドメイン名と Windows ユーザー名が提供されます。</span><span class="sxs-lookup"><span data-stu-id="2c63c-113">The Active Directory Management Agent provides the Windows domain name and Windows user name for the mapping.</span></span> <span data-ttu-id="2c63c-114">この Active Directory 管理マネージャ インスタンスの名前は、MIIS の Active Directory 管理エージェント インスタンスの名前と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c63c-114">This Active Directory Management Agent instance name must match the name of an Active Directory Management Agent instance in MIIS.</span></span>  
  
 <span data-ttu-id="2c63c-115">**属性: deleteAll** - 省略可能です。 既定値は`true`します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-115">**Attribute: deleteAll** - Optional; default is `true`.</span></span> <span data-ttu-id="2c63c-116">これを `true` に設定し、Windows ID を削除すると、すべての ENTSSO アプリケーションから、その Windows ID とのマッピングがすべて削除されます。</span><span class="sxs-lookup"><span data-stu-id="2c63c-116">If this is set to `true`, and a Windows identity is deleted, all mappings with that Windows identity are deleted from all ENTSSO applications.</span></span>  
  
 <span data-ttu-id="2c63c-117">**要素: アプリケーション**-SSO 関連アプリケーションと外部管理エージェントの間のリレーションシップを定義します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-117">**Element: Application** - Defines the relationship between an SSO affiliate application and an external Management Agent.</span></span> <span data-ttu-id="2c63c-118">複数の `Application` 要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c63c-118">Multiple `Application` elements are allowed.</span></span>  
  
 <span data-ttu-id="2c63c-119">**属性: 名前**-SSO 関連アプリケーションの名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-119">**Attribute: name** - Defines the name of the SSO affiliate application.</span></span> <span data-ttu-id="2c63c-120">このアプリケーションは、ENTSSO システム内に既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c63c-120">This application must already exist within the ENTSSO system.</span></span>  
  
 <span data-ttu-id="2c63c-121">**属性: sourceMA** -ソース (外部) のインスタンス名を定義します。 このアプリケーションのマッピングの外部 UserId を提供するために使用する管理エージェント。</span><span class="sxs-lookup"><span data-stu-id="2c63c-121">**Attribute: sourceMA** - Defines the instance name for the source (external) Management Agent that will be used to provide the external UserId in the mapping for this application.</span></span> <span data-ttu-id="2c63c-122">この外部管理エージェント インスタンスの名前は、MIIS の外部 MA インスタンスの名前と一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c63c-122">This external Management Agent instance name must match the name of an external MA instance in MIIS.</span></span>  
  
 <span data-ttu-id="2c63c-123">**属性: 作成**- 省略可能です。 既定値は`true`します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-123">**Attribute: create** - Optional; default is `true`.</span></span> <span data-ttu-id="2c63c-124">このアプリケーションのマッピングを作成するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-124">Defines whether mappings should be created for this application.</span></span>  
  
 <span data-ttu-id="2c63c-125">**属性: 削除**- 省略可能です。 既定値は`true`します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-125">**Attribute: delete** - Optional; default is `true`.</span></span> <span data-ttu-id="2c63c-126">このアプリケーションのマッピングを削除するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-126">Defines whether mappings should be deleted for this application.</span></span>  
  
 <span data-ttu-id="2c63c-127">**要素: SourceMA** - 省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2c63c-127">**Element: SourceMA** - Optional.</span></span> <span data-ttu-id="2c63c-128">特定のソース (外部) 管理エージェント インスタンスのオブジェクト型と属性名を示します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-128">Identifies the object type and attribute names for a specific source (external) Management Agent instance.</span></span> <span data-ttu-id="2c63c-129">特定の管理エージェントに関するこの要素がない場合は、既定のオブジェクト型 ("person") と属性名 ("uid") が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c63c-129">If this element is not present for a specific Management Agent, then the default object type (“person”) and attribute names (“uid”) are assumed.</span></span> <span data-ttu-id="2c63c-130">複数の `SourceMA` 要素を使用できます。</span><span class="sxs-lookup"><span data-stu-id="2c63c-130">Multiple `SourceMA` elements are allowed.</span></span>  
  
 <span data-ttu-id="2c63c-131">**属性: 名前**-ソース (外部) の名前の管理エージェント。</span><span class="sxs-lookup"><span data-stu-id="2c63c-131">**Attribute: name** - The name of the source (external) Management Agent.</span></span> <span data-ttu-id="2c63c-132">この名前は、`sourceMA` 要素の `Application` 属性の名前の少なくとも 1 つと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c63c-132">This name must match at least one of the `sourceMA` attribute names from the `Application` elements.</span></span>  
  
 <span data-ttu-id="2c63c-133">**属性: objectType** - 省略可能です。 既定値は`person`します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-133">**Attribute: objectType** - Optional; default is `person`.</span></span> <span data-ttu-id="2c63c-134">外部 UserId を提供する管理エージェントのオブジェクト型名が `person` でない場合は、ここで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c63c-134">If the object type name that provides the external UserId is not `person`, it should be specified here.</span></span>  
  
 <span data-ttu-id="2c63c-135">**属性: 属性の**- 省略可能です。 既定値は`uid`します。</span><span class="sxs-lookup"><span data-stu-id="2c63c-135">**Attribute: attribute** - Optional; default is `uid`.</span></span> <span data-ttu-id="2c63c-136">外部 UserId を提供する管理エージェントの属性名が `uid` でない場合は、ここで指定できます。</span><span class="sxs-lookup"><span data-stu-id="2c63c-136">If the attribute name that provides the external UserId is not `uid`, you can specify it here.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c63c-137">参照</span><span class="sxs-lookup"><span data-stu-id="2c63c-137">See Also</span></span>  
 [<span data-ttu-id="2c63c-138">ENTSSO 管理エージェントを使用する方法</span><span class="sxs-lookup"><span data-stu-id="2c63c-138">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)