---
title: アダプター WSDL ファイル |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d4b35c0-1e4b-4106-8921-29d14f976d65
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c600729411066637e021a118b88ec97ffd3b25fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22229826"
---
# <a name="adapter-wsdl-files"></a><span data-ttu-id="ad2d3-102">アダプター WSDL ファイル</span><span class="sxs-lookup"><span data-stu-id="ad2d3-102">Adapter WSDL Files</span></span>
<span data-ttu-id="ad2d3-103">Web サービス記述言語 (WSDL) ファイルの選択し、では、入力アダプター メタデータの追加ウィザードで、 **インポートするサービス**ページ。</span><span class="sxs-lookup"><span data-stu-id="ad2d3-103">In the Add Adapter Metadata Wizard the Web Services Description Language (WSDL) file is selected and input on the **Select Services to Import** page.</span></span> <span data-ttu-id="ad2d3-104">ウィザードは、サービスによって公開され、ユーザーが選択した WSDL ファイルを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="ad2d3-104">The wizard reads the WSDL files exposed by the service and selected by the user.</span></span> <span data-ttu-id="ad2d3-105">その後、XSD ファイルとオーケストレーションを作成して BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="ad2d3-105">It then creates and adds an XSD file and an orchestration in the BizTalk project.</span></span>  
  
 <span data-ttu-id="ad2d3-106">サンプル ファイル アダプターでは、Service1.wsdl ファイルに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がプロジェクトに追加する XSD 定義が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ad2d3-106">In the sample file adapter, the Service1.wsdl file contains the XSD definitions that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adds to the project.</span></span> <span data-ttu-id="ad2d3-107">Service1.wsdl ファイルを変更することも、BizTalk プロジェクトに追加する XSD 定義を含む独自の WSDL ファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="ad2d3-107">You may choose to modify the Service1.wsdl file or create your own WSDL file that contains the XSD definitions to add to your BizTalk project.</span></span>  
  
 <span data-ttu-id="ad2d3-108">次のコードは、Service1.wsdl ファイルの一部です。</span><span class="sxs-lookup"><span data-stu-id="ad2d3-108">The following code is from the Service1.wsdl file:</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<definitions xmlns:http="http://schemas.xmlsoap.org/wsdl/http/" xmlns:soap="http://schemas.xmlsoap.org/wsdl/soap/" xmlns:s="http://www.w3.org/2001/XMLSchema" xmlns:s0="http://tempuri.org/" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:tm="http://microsoft.com/wsdl/mime/textMatching/" xmlns:mime="http://schemas.xmlsoap.org/wsdl/mime/" targetNamespace="http://tempuri.org/" xmlns="http://schemas.xmlsoap.org/wsdl/">  
  <types>  
    <s:schema elementFormDefault="qualified" targetNamespace="http://tempuri.org/">  
      <s:element name="GetTaxID">  
        <s:complexType />  
      </s:element>  
      <s:element name="GetTaxIDResponse">  
        <s:complexType>  
          <s:sequence>  
            <s:element minOccurs="0" maxOccurs="1" name="GetTaxIDResult" type="s:string" />  
          </s:sequence>  
        </s:complexType>  
      </s:element>  
      <s:element name="GetPayStub">  
        <s:complexType />  
      </s:element>  
      <s:element name="GetPayStubResponse">  
        <s:complexType>  
          <s:sequence>  
            <s:element minOccurs="0" maxOccurs="1" name="GetPayStubResult" type="s:string" />  
          </s:sequence>  
        </s:complexType>  
      </s:element>  
      <s:element name="GetTaxInfo">  
        <s:complexType />  
      </s:element>  
  
```