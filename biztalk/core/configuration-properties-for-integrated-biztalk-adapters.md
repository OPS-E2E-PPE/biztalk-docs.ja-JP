---
title: 統合 BizTalk アダプターの構成プロパティ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, security
- adapters, passwords
- IReceiveLocation.CustomData property
- security, passwords
- ISendPort.CustomData property
- binding files, passwords
- adapters, properties
- binding files, security
ms.assetid: 4780a558-4322-428a-aa4a-0c32913faded
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eac9263364bc4342fd2bdbcd484e9aa150deb82
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391486"
---
# <a name="configuration-properties-for-integrated-biztalk-adapters"></a><span data-ttu-id="42e73-102">統合 BizTalk アダプターの構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="42e73-102">Configuration Properties for Integrated BizTalk Adapters</span></span>
<span data-ttu-id="42e73-103">BizTalk エクスプローラ オブジェクト モデルを公開、 **IReceiveLocation.CustomData**と**ISendPort.CustomData**名前/値の形式でアダプター構成プロパティ バッグを含むプロパティ組の XML 文字列。</span><span class="sxs-lookup"><span data-stu-id="42e73-103">The BizTalk Explorer object model exposes the **IReceiveLocation.CustomData** and **ISendPort.CustomData** properties that contain the adapter configuration property bag in the form of a name/value pair XML string.</span></span> <span data-ttu-id="42e73-104">この名前/値ペアの XML 文字列が格納されている、 \<CustomProps\>内の要素を\<TransportTypeData\>バインド ファイル内の要素。</span><span class="sxs-lookup"><span data-stu-id="42e73-104">This name/value pair XML string is stored in a \<CustomProps\> element within a \<TransportTypeData\> element in a binding file.</span></span> <span data-ttu-id="42e73-105">ほとんどの情報の\<CustomProps\>要素は、アダプターの BizTalk Server のユーザー インターフェイス (など、BizTalk 管理コンソールまたは BizTalk エクスプ ローラー) に設定できる情報に対応します。</span><span class="sxs-lookup"><span data-stu-id="42e73-105">Most of the information in the \<CustomProps\> element corresponds to information that can be set for an adapter in the BizTalk Server user interface (such as the BizTalk Administration Console or BizTalk Explorer).</span></span> <span data-ttu-id="42e73-106">適用されるこれらの値がバインド ファイルに存在する場合は、指定したアダプターの構成を受信場所と、送信ポートのバインド ファイルのインポート時に。</span><span class="sxs-lookup"><span data-stu-id="42e73-106">If these values are present in a binding file then they are applied to the adapter configuration for the specified receive locations and send ports when the binding file is imported.</span></span> <span data-ttu-id="42e73-107">すべてのアダプターの構成情報は、シングル サインオン データベースに格納されます。</span><span class="sxs-lookup"><span data-stu-id="42e73-107">Configuration information for all adapters is stored in the Single Sign-On database.</span></span>  
  
 <span data-ttu-id="42e73-108">このセクションでは、各統合 BizTalk アダプターを設定できる構成プロパティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="42e73-108">This section describes the configuration properties that can be set for each integrated BizTalk adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42e73-109">パスワードの情報に格納されている、 \<TransportTypeData\>バインド ファイルの要素をマスクする機微なデータがクリア テキストで保存しないようにします。</span><span class="sxs-lookup"><span data-stu-id="42e73-109">Password information that is stored in the \<TransportTypeData\> element of a binding file is masked so that sensitive data is not saved in clear text.</span></span> <span data-ttu-id="42e73-110">トランスポートに応じて、パスワードの情報は NULL に置き換えられますかまたはアスタリスクに置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="42e73-110">Depending on the transport, password information is either replaced with NULL or is replaced with asterisks.</span></span> <span data-ttu-id="42e73-111">この情報は、ターゲットの BizTalk Server の構成にバインド ファイルをインポートする前にアダプター構成を更新するバインド ファイルに手動で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="42e73-111">You must manually enter this information in the binding file to update the adapter configuration before importing the binding file into the target BizTalk Server configuration.</span></span>  
  
 <span data-ttu-id="42e73-112">アダプター フレームワークを使用して構築されたアダプターの構成データが格納されている、 \<AdapterConfig\>要素。</span><span class="sxs-lookup"><span data-stu-id="42e73-112">The configuration data for adapters built using the Adapter Framework is stored in an \<AdapterConfig\> element.</span></span> <span data-ttu-id="42e73-113">\<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データ型、 **\< \>** この要素に含まれる文字をエスケープする必要がありますまたはエラーが発生時にします。バインド ファイルをインポートしようとしてください。</span><span class="sxs-lookup"><span data-stu-id="42e73-113">Since the \<AdapterConfig\> element specifies the VT_BSTR (vt="8") data type, the **\< \>** characters contained in this element must be escaped or an error will occur when you attempt to import the binding file.</span></span> <span data-ttu-id="42e73-114">これにより、テキストは小さい値を指定する構成データを人間がこれらの文字をエスケープしない場合よりも読みやすくします。</span><span class="sxs-lookup"><span data-stu-id="42e73-114">This causes the text for the configuration data to be less human readable than if these characters were not escaped.</span></span> <span data-ttu-id="42e73-115">次の例を POP3 アダプターにバインドされた送信ポートのサンプル構成データからこれらの文字をエスケープする効果を示しています。</span><span class="sxs-lookup"><span data-stu-id="42e73-115">The following example illustrates the effect of escaping these characters from sample configuration data for a send port bound to the POP3 adapter.</span></span>  
  
 <span data-ttu-id="42e73-116">**TransportTypeData 構成データで使用される <> 文字をエスケープしませんが、 \<AdapterConfig\>要素**</span><span class="sxs-lookup"><span data-stu-id="42e73-116">**TransportTypeData configuration data that does not escape the <> characters used in the \<AdapterConfig\> element**</span></span>  
  
 <span data-ttu-id="42e73-117">この構成データが無効ですので、 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データ型と\<\>に含まれる文字、 \<AdapterConfig\>要素はエスケープされません。</span><span class="sxs-lookup"><span data-stu-id="42e73-117">This configuration data is invalid because the \<AdapterConfig\> element specifies the VT_BSTR (vt="8") data type and the \< \> characters contained in the \<AdapterConfig\> element are not escaped:</span></span>  
  
```  
<TransportTypeData>  
<CustomProps>  
<AdapterConfig vt="8">  
<Config xmlns:xsi=http://www.w3.org/2001/XMLSchema-instance xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<mailServer>test.microsoft.com</mailServer>  
<serverPort>0</serverPort>  
<userName>testuser</userName>  
<password>******</password>  
<authenticationScheme>Basic</authenticationScheme>  
<sslRequired>false</sslRequired>  
<applyMIME>true</applyMIME>  
<bodyPartContentType>text/xml</bodyPartContentType>  
<bodyPartIndex>1</bodyPartIndex>  
<errorThreshold>10</errorThreshold>  
<pollingInterval>5</pollingInterval>  
<pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure>   
<uri>POP3://test.microsoft.com#testuser</uri>  
</Config>  
</AdapterConfig>  
</CustomProps>  
</TransportTypeData>  
```  
  
 <span data-ttu-id="42e73-118">**使用される <> 文字がエスケープされる TransportTypeData 構成データ、 \<AdapterConfig\>要素**</span><span class="sxs-lookup"><span data-stu-id="42e73-118">**TransportTypeData configuration data that does escape the <> characters used in the \<AdapterConfig\> element**</span></span>  
  
 <span data-ttu-id="42e73-119">以降、 \<AdapterConfig\>要素は VT_BSTR を指定します (vt =「8」) データ型、 \< \>から文字をエスケープする必要があります、 \<AdapterConfig\>要素を次に示すように。</span><span class="sxs-lookup"><span data-stu-id="42e73-119">Since the \<AdapterConfig\> element specifies the VT_BSTR (vt="8") data type, the \< \> characters must be escaped from the \<AdapterConfig\> element as seen below:</span></span>  
  
```  
<TransportTypeData>  
<CustomProps>  
<AdapterConfig vt="8">  
<Config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"  
xmlns:xsd="http://www.w3.org/2001/XMLSchema"><mailServer>test  
microsoft.com</mailServer><serverPort>0</serverPort>&  
lt;userName>testuser</userName><password>******</pass  
word><authenticationScheme>Basic</authenticationScheme>&  
lt;sslRequired>false</sslRequired><applyMIME>true</ap  
plyMIME><bodyPartContentType>text/xml</bodyPartContentType&  
gt;<bodyPartIndex>1</bodyPartIndex><errorThreshold>10  
</errorThreshold><pollingInterval>5</pollingInterval>  
<pollingUnitOfMeasure>Minutes</pollingUnitOfMeasure><uri  
>POP3://test.microsoft.com#testuser</uri></Config>  
</AdapterConfig>  
</CustomProps>  
</TransportTypeData>  
```  
  
 <span data-ttu-id="42e73-120">アダプター フレームワークで作成された統合アダプターを以下に示します。</span><span class="sxs-lookup"><span data-stu-id="42e73-120">The integrated adapters that were created with the Adapter Framework include the following:</span></span>  
  
- <span data-ttu-id="42e73-121">FTP アダプター</span><span class="sxs-lookup"><span data-stu-id="42e73-121">FTP Adapter</span></span>  
  
- <span data-ttu-id="42e73-122">MQSeries アダプター</span><span class="sxs-lookup"><span data-stu-id="42e73-122">MQSeries Adapter</span></span>  
  
- <span data-ttu-id="42e73-123">MSMQ アダプター</span><span class="sxs-lookup"><span data-stu-id="42e73-123">MSMQ Adapter</span></span>  
  
- <span data-ttu-id="42e73-124">POP3 アダプター</span><span class="sxs-lookup"><span data-stu-id="42e73-124">POP3 Adapter</span></span>  
  
- <span data-ttu-id="42e73-125">Windows Sharepoint Services アダプター</span><span class="sxs-lookup"><span data-stu-id="42e73-125">Windows Sharepoint Services Adapter</span></span>  
  
  <span data-ttu-id="42e73-126">各統合アダプターの TransportTypeData 構成データとして使用するサンプル文字列を表示するには、このセクションでは、アダプターに関連付けられている構成プロパティのトピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="42e73-126">To view a sample string used as the TransportTypeData configuration data for each integrated adapter, please see the configuration properties topic that is associated with the adapter in this section.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="42e73-127">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="42e73-127">In This Section</span></span>  
 [<span data-ttu-id="42e73-128">構成プロパティの変数の型</span><span class="sxs-lookup"><span data-stu-id="42e73-128">Configuration Property Variable Types</span></span>](../core/configuration-property-variable-types.md)  
  
 [<span data-ttu-id="42e73-129">ファイル アダプター構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="42e73-129">File Adapter Configuration Properties</span></span>](../core/file-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="42e73-130">FTP アダプター構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="42e73-130">FTP Adapter Configuration Properties</span></span>](../core/ftp-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="42e73-131">HTTP アダプター構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="42e73-131">HTTP Adapter Configuration Properties</span></span>](../core/http-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="42e73-132">MQSeries アダプター構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="42e73-132">MQSeries Adapter Configuration Properties</span></span>](../core/mqseries-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="42e73-133">MSMQ アダプター構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="42e73-133">MSMQ Adapter Configuration Properties</span></span>](../core/msmq-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="42e73-134">POP3 アダプター構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="42e73-134">POP3 Adapter Configuration Properties</span></span>](../core/pop3-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="42e73-135">SMTP アダプター構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="42e73-135">SMTP Adapter Configuration Properties</span></span>](../core/smtp-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="42e73-136">SOAP アダプター構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="42e73-136">SOAP Adapter Configuration Properties</span></span>](../core/soap-adapter-configuration-properties.md)  
  
 [<span data-ttu-id="42e73-137">Windows SharePoint Services アダプターの構成プロパティ</span><span class="sxs-lookup"><span data-stu-id="42e73-137">Windows Sharepoint Services Adapter Configuration Properties</span></span>](../core/windows-sharepoint-services-adapter-configuration-properties.md)