---
title: XML ファイルの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 52851901-8374-412f-9c29-83845d8d4861
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a41fdd9689f822736607ecbc7ec1ea0f0fd4f36c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355059"
---
# <a name="configuring-the-xml-file"></a><span data-ttu-id="4bb72-102">XML ファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-102">Configuring the XML File</span></span>
<span data-ttu-id="4bb72-103">エンタープライズ シングル サインオン (SSO) をインストールするときに ENTSSO.xml という XML ファイルが Extensions ディレクトリにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="4bb72-103">When you install Enterprise Single Sign-On (SSO), an XML file named ENTSSO.xml is installed in your Extensions directory.</span></span> <span data-ttu-id="4bb72-104">ファイルを編集するには、ENTSSO 管理エージェント (MA) のすべてのインスタンスの構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-104">By editing the file, you define the configuration for all instances of the ENTSSO Management Agent (MA).</span></span>  
  
 <span data-ttu-id="4bb72-105">ファイルは、次のような。</span><span class="sxs-lookup"><span data-stu-id="4bb72-105">The file is similar to the following:</span></span>  
  
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
  
## <a name="xml-elements-and-attributes"></a><span data-ttu-id="4bb72-106">XML 要素と属性</span><span class="sxs-lookup"><span data-stu-id="4bb72-106">XML Elements and Attributes</span></span>  
 <span data-ttu-id="4bb72-107">次の一覧には、要素と XML ファイルで定義する属性について説明します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-107">The following list describes the elements and attributes that you define in the XML file.</span></span> <span data-ttu-id="4bb72-108">このファイル内のすべての要素と属性名は大文字小文字が区別ことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4bb72-108">Note that all element and attribute names in this file are case sensitive.</span></span>  
  
 <span data-ttu-id="4bb72-109">**要素:ENTSSO** -単一の ENTSSO MA インスタンスの構成を定義します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-109">**Element: ENTSSO** - Defines the configuration of a single ENTSSO MA instance.</span></span> <span data-ttu-id="4bb72-110">複数の ENTSSO 要素が許可されます。</span><span class="sxs-lookup"><span data-stu-id="4bb72-110">Multiple ENTSSO elements are allowed.</span></span>  
  
 <span data-ttu-id="4bb72-111">**属性: 名前**-、ENTSSO 管理エージェントのインスタンスの名前を定義し、Microsoft Identity Integration Server (MIIS) の ENTSSO 管理エージェント インスタンスの名前に一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb72-111">**Attribute: name** - Defines the instance name of the ENTSSO Management Agent, and must match the name of the ENTSSO Management Agent instance in Microsoft Identity Integration Server (MIIS).</span></span>  
  
 <span data-ttu-id="4bb72-112">**属性: adma** -この ENTSSO 管理エージェント インスタンスによって使用される Active Directory 管理エージェントのインスタンスの名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-112">**Attribute: adma** - Defines the instance name of the Active Directory Management Agent that will be used by this ENTSSO Management Agent instance.</span></span> <span data-ttu-id="4bb72-113">Active Directory 管理エージェントは、Windows ドメイン名と Windows ユーザー名マッピングを提供します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-113">The Active Directory Management Agent provides the Windows domain name and Windows user name for the mapping.</span></span> <span data-ttu-id="4bb72-114">この Active Directory 管理エージェント インスタンスの名前は、MIIS の Active Directory 管理エージェント インスタンスの名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb72-114">This Active Directory Management Agent instance name must match the name of an Active Directory Management Agent instance in MIIS.</span></span>  
  
 <span data-ttu-id="4bb72-115">**属性: deleteAll** - 省略可能です。 既定値は`true`します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-115">**Attribute: deleteAll** - Optional; default is `true`.</span></span> <span data-ttu-id="4bb72-116">設定されている場合`true`、および、Windows id を削除すると、その Windows id を持つすべてのマッピングは、すべての ENTSSO アプリケーションから削除されます。</span><span class="sxs-lookup"><span data-stu-id="4bb72-116">If this is set to `true`, and a Windows identity is deleted, all mappings with that Windows identity are deleted from all ENTSSO applications.</span></span>  
  
 <span data-ttu-id="4bb72-117">**要素:アプリケーション**-SSO 関連アプリケーションと外部管理エージェント間のリレーションシップを定義します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-117">**Element: Application** - Defines the relationship between an SSO affiliate application and an external Management Agent.</span></span> <span data-ttu-id="4bb72-118">複数`Application`要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-118">Multiple `Application` elements are allowed.</span></span>  
  
 <span data-ttu-id="4bb72-119">**属性: 名前**-SSO 関連アプリケーションの名前を定義します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-119">**Attribute: name** - Defines the name of the SSO affiliate application.</span></span> <span data-ttu-id="4bb72-120">このアプリケーションは、ENTSSO システム内で既に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb72-120">This application must already exist within the ENTSSO system.</span></span>  
  
 <span data-ttu-id="4bb72-121">**属性: sourceMA** -ソース (外部) のインスタンス名を定義します。 このアプリケーションのマッピングの外部 UserId を提供するために使用する管理エージェント。</span><span class="sxs-lookup"><span data-stu-id="4bb72-121">**Attribute: sourceMA** - Defines the instance name for the source (external) Management Agent that will be used to provide the external UserId in the mapping for this application.</span></span> <span data-ttu-id="4bb72-122">この外部管理エージェント インスタンスの名前は、MIIS の外部 MA インスタンスの名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb72-122">This external Management Agent instance name must match the name of an external MA instance in MIIS.</span></span>  
  
 <span data-ttu-id="4bb72-123">**属性: 作成**- 省略可能です。 既定値は`true`します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-123">**Attribute: create** - Optional; default is `true`.</span></span> <span data-ttu-id="4bb72-124">このアプリケーションのマッピングを作成するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-124">Defines whether mappings should be created for this application.</span></span>  
  
 <span data-ttu-id="4bb72-125">**属性: 削除**- 省略可能です。 既定値は`true`します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-125">**Attribute: delete** - Optional; default is `true`.</span></span> <span data-ttu-id="4bb72-126">このアプリケーションのマッピングを削除するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-126">Defines whether mappings should be deleted for this application.</span></span>  
  
 <span data-ttu-id="4bb72-127">**要素:SourceMA** - 省略可能。</span><span class="sxs-lookup"><span data-stu-id="4bb72-127">**Element: SourceMA** - Optional.</span></span> <span data-ttu-id="4bb72-128">特定のソース (外部) 管理エージェント インスタンスのオブジェクトの種類と属性名を識別します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-128">Identifies the object type and attribute names for a specific source (external) Management Agent instance.</span></span> <span data-ttu-id="4bb72-129">この要素が特定の管理エージェントの存在しない場合、既定のオブジェクト型 ("person") と属性名 ("uid") と見なされます。</span><span class="sxs-lookup"><span data-stu-id="4bb72-129">If this element is not present for a specific Management Agent, then the default object type (“person”) and attribute names (“uid”) are assumed.</span></span> <span data-ttu-id="4bb72-130">複数`SourceMA`要素を使用します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-130">Multiple `SourceMA` elements are allowed.</span></span>  
  
 <span data-ttu-id="4bb72-131">**属性: 名前**-ソース (外部) の名前の管理エージェント。</span><span class="sxs-lookup"><span data-stu-id="4bb72-131">**Attribute: name** - The name of the source (external) Management Agent.</span></span> <span data-ttu-id="4bb72-132">この名前には、少なくとも 1 つの一致する必要があります、`sourceMA`属性の名前、`Application`要素。</span><span class="sxs-lookup"><span data-stu-id="4bb72-132">This name must match at least one of the `sourceMA` attribute names from the `Application` elements.</span></span>  
  
 <span data-ttu-id="4bb72-133">**属性: objectType** - 省略可能です。 既定値は`person`します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-133">**Attribute: objectType** - Optional; default is `person`.</span></span> <span data-ttu-id="4bb72-134">外部 UserId を提供するオブジェクトの型名がない`person`、ここで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4bb72-134">If the object type name that provides the external UserId is not `person`, it should be specified here.</span></span>  
  
 <span data-ttu-id="4bb72-135">**属性: 属性の**- 省略可能です。 既定値は`uid`します。</span><span class="sxs-lookup"><span data-stu-id="4bb72-135">**Attribute: attribute** - Optional; default is `uid`.</span></span> <span data-ttu-id="4bb72-136">外部 UserId を提供する属性名がない`uid`、ここで指定できます。</span><span class="sxs-lookup"><span data-stu-id="4bb72-136">If the attribute name that provides the external UserId is not `uid`, you can specify it here.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bb72-137">参照</span><span class="sxs-lookup"><span data-stu-id="4bb72-137">See Also</span></span>  
 [<span data-ttu-id="4bb72-138">ENTSSO 管理エージェントを使用する方法</span><span class="sxs-lookup"><span data-stu-id="4bb72-138">How to Use the ENTSSO Management Agent</span></span>](../core/how-to-use-the-entsso-management-agent.md)