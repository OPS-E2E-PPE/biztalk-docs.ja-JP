---
title: アダプター WSDL ファイル |Microsoft Docs
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
ms.openlocfilehash: 67b341372e39fc9f834c2240127d10946def76a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361160"
---
# <a name="adapter-wsdl-files"></a><span data-ttu-id="860a8-102">アダプター WSDL ファイル</span><span class="sxs-lookup"><span data-stu-id="860a8-102">Adapter WSDL Files</span></span>
<span data-ttu-id="860a8-103">Web サービス記述言語 (WSDL) ファイルの選択し、では、入力アダプター メタデータの追加ウィザードで、 **インポートするサービス**ページ。</span><span class="sxs-lookup"><span data-stu-id="860a8-103">In the Add Adapter Metadata Wizard the Web Services Description Language (WSDL) file is selected and input on the **Select Services to Import** page.</span></span> <span data-ttu-id="860a8-104">ウィザードでは、WSDL ファイルは、サービスによって公開され、ユーザーが選択したを読み取ります。</span><span class="sxs-lookup"><span data-stu-id="860a8-104">The wizard reads the WSDL files exposed by the service and selected by the user.</span></span> <span data-ttu-id="860a8-105">作成し、XSD ファイルとオーケストレーションを BizTalk プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="860a8-105">It then creates and adds an XSD file and an orchestration in the BizTalk project.</span></span>  
  
 <span data-ttu-id="860a8-106">Service1.wsdl ファイルは、サンプル ファイル アダプターの XSD 定義を含むを[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]をプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="860a8-106">In the sample file adapter, the Service1.wsdl file contains the XSD definitions that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adds to the project.</span></span> <span data-ttu-id="860a8-107">Service1.wsdl ファイルを変更するか、BizTalk プロジェクトに追加する XSD 定義を含む独自の WSDL ファイルを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="860a8-107">You may choose to modify the Service1.wsdl file or create your own WSDL file that contains the XSD definitions to add to your BizTalk project.</span></span>  
  
 <span data-ttu-id="860a8-108">次のコードは、Service1.wsdl ファイルです。</span><span class="sxs-lookup"><span data-stu-id="860a8-108">The following code is from the Service1.wsdl file:</span></span>  
  
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