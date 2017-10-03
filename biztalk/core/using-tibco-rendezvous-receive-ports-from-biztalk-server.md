---
title: "使用して TIBCO Rendezvous 受信ポートを BizTalk Server から |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: receive ports, using from BizTalk Server
ms.assetid: 26cb20f9-4d26-48f6-a5e9-a51348a56538
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b8e0999362844570bb56cfbc488e5fd5775e286
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="using-tibco-rendezvous-receive-ports-from-biztalk-server"></a><span data-ttu-id="82379-102">BizTalk Server からの TIBCO Rendezvous 受信ポートの使用</span><span class="sxs-lookup"><span data-stu-id="82379-102">Using TIBCO Rendezvous Receive Ports from BizTalk Server</span></span>
<span data-ttu-id="82379-103">受信ポートを使用するには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に受信メッセージのスキーマを提供します。</span><span class="sxs-lookup"><span data-stu-id="82379-103">To use a receive port, you can provide a schema to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for the incoming messages.</span></span> <span data-ttu-id="82379-104">受信ポートは、サブジェクト名の特定のセットを待機するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="82379-104">A receive port is configured to listen for a particular set of subject names.</span></span> <span data-ttu-id="82379-105">受信ポートでは、オプションのワイルドカード文字と共にサブジェクト名を使用して、複数のサブジェクト名が照合されます。</span><span class="sxs-lookup"><span data-stu-id="82379-105">It uses a subject name with optional wildcard characters to match multiple subject names.</span></span> <span data-ttu-id="82379-106">ユーザーは、特定の文字列に一致する可能性のあるサブジェクトごとに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オーケストレーションで異なるポート操作を定義します。</span><span class="sxs-lookup"><span data-stu-id="82379-106">You define different port operations in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for each possible subject that matches the given string.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82379-107">アダプターは、オーケストレーションとメッセージ シナリオの両方をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="82379-107">The Adapter supports both orchestration and messaging scenarios.</span></span>  
  
## <a name="defining-schemas"></a><span data-ttu-id="82379-108">スキーマの定義</span><span class="sxs-lookup"><span data-stu-id="82379-108">Defining Schemas</span></span>  
 <span data-ttu-id="82379-109">たとえば、ポートが、サブジェクト名をリッスンするように構成されている場合**STOCK です。マーケットです。インデックス。 >** ('**>**' は、右側に何を意味するワイルドカード文字)、などのサブジェクト名の操作を定義する有効なことになります**STOCK です。マーケットです。インデックスです。NYSE です。SP500**、 **STOCK です。マーケットです。インデックスです。TSX.TSX60**のようにします。</span><span class="sxs-lookup"><span data-stu-id="82379-109">For example, if the port is configured to listen to the subject name, **STOCK.MARKET.INDICES.>** ('**>**' is a wildcard character that means anything else to the right), it would be valid to define operations for subject names such as **STOCK.MARKET.INDICES.NYSE.SP500**, **STOCK.MARKET.INDICES.TSX.TSX60**, and so on.</span></span> <span data-ttu-id="82379-110">説明している方法を使用してメッセージがアダプターにより生成[TIBCO Rendezvous の受信ハンドラーのデータ型マッピング](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)、ルート要素名と名前空間のリッスンに基づくを生成および名と受信したメッセージの件名それぞれのサブジェクト名します。</span><span class="sxs-lookup"><span data-stu-id="82379-110">The adapter generates messages using the strategy described in [Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md), and generates the root element name and namespaces based on the listen subject name and received message subject names respectively.</span></span>  
  
 <span data-ttu-id="82379-111">前の例では、アダプターには、SP500 イベントの次のようなメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="82379-111">In the previous example, the adapter generates a message that looks like this for the SP500 event:</span></span>  
  
```  
<ns:STOCK.MARKET.INDICES.NYSE.SP500 xmlns:ns='   
http://schemas.microsoft.com/TibcoRendezvous/Types/  
STOCK.MARKET.INDICES.NYSE.GTWILDCARD'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types' … >  
<message body>  
</ns: STOCK.MARKET.INDICES.NYSE.SP500>  
  
```  
  
 <span data-ttu-id="82379-112">同じ規則を使用するスキーマを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82379-112">You must define a schema that uses the same conventions.</span></span> <span data-ttu-id="82379-113">例:</span><span class="sxs-lookup"><span data-stu-id="82379-113">For example:</span></span>  
  
```  
<xsd:schema  
targetNamespace='   
  
http://schemas.microsoft.com/TibcoRendezvous/Types/STOCK.MARKET.INDICES.N  
YSE.GTWILDCARD'  
xmlns:xsd=' http://www.w3.org/2001/XMLSchema'  
xmlns:tibrv=' http://schemas.microsoft.com/TibcoRendezvous/Types'>  
xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
<xsd:element name='STOCK.MARKET.INDICES.NYSE.SP500'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_NYSE_SP500" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<SP500 message definitions goes here>  
</xsd:complexType>  
<xsd:element name='STOCK.MARKET.INDICES.TSX.TSX60'>  
  
 <xs:annotation>  
   <xs:appinfo>  
     <b:recordInfo rootTypeName="STOCK_MARKET_INDICES_TSX_TSX60" />  
   </xs:appinfo>  
  
 </xs:annotation>  
<xsd:complexType>  
<TSX60 message definitions goes here>  
</xsd:complexType>  
  
```  
  
 <span data-ttu-id="82379-114">使用に注意してください、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] **recordInfo/rootTypeName**注釈。</span><span class="sxs-lookup"><span data-stu-id="82379-114">Note the use of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**recordInfo/rootTypeName** annotation.</span></span> <span data-ttu-id="82379-115">これは、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk Integration に対して、ドットを含む名前ではなく、生成された .NET Framework の種類の名前を使用するように指定しています。</span><span class="sxs-lookup"><span data-stu-id="82379-115">This is to instruct the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]/BizTalk integration to use that name for the generated .NET Framework types, instead of the name that contains dots.</span></span> <span data-ttu-id="82379-116">任意のものを指定できます。</span><span class="sxs-lookup"><span data-stu-id="82379-116">You can specify anything.</span></span> <span data-ttu-id="82379-117">例では、ドットはアンダースコアに置き換えられています。</span><span class="sxs-lookup"><span data-stu-id="82379-117">In the examples, the dots are replaced with underscores.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="82379-118">ドットにより、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 開発ツールによって無効な名前が生成されます。</span><span class="sxs-lookup"><span data-stu-id="82379-118">The dots cause invalid names to be generated by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] development tools.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82379-119">参照</span><span class="sxs-lookup"><span data-stu-id="82379-119">See Also</span></span>  
 <span data-ttu-id="82379-120">[TIBCO Rendezvous でのデータ型マッピングの受信ハンドラー](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span><span class="sxs-lookup"><span data-stu-id="82379-120">[Data Type Mapping for Receive Handlers in TIBCO Rendezvous](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md) </span></span>  
 [<span data-ttu-id="82379-121">作成元の TIBCO Rendezvous 受信ハンドラー</span><span class="sxs-lookup"><span data-stu-id="82379-121">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)