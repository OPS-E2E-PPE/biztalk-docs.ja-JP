---
title: WCF LOB Adapter SDK を持つアダプターのトレース |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7a4f4758-3e3e-48c4-b4cf-414c2b05d539
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ca4b68f23f791de3ecd68bc69b85c2908b6d7a0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25965360"
---
# <a name="trace-an-adapter-with-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="0ee52-102">WCF LOB Adapter SDK を持つアダプターをトレースします。</span><span class="sxs-lookup"><span data-stu-id="0ee52-102">Trace an adapter with the WCF LOB Adapter SDK</span></span>
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<span data-ttu-id="0ee52-103">トレースは、Systems.Diagnostics 上に作成されています。</span><span class="sxs-lookup"><span data-stu-id="0ee52-103"> tracing is built on top of Systems.Diagnostics.</span></span> <span data-ttu-id="0ee52-104">Microsoft.ServiceModel.Channels トレース ソースを使用する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム。</span><span class="sxs-lookup"><span data-stu-id="0ee52-104">You use Microsoft.ServiceModel.Channels trace source for the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] runtime.</span></span>  <span data-ttu-id="0ee52-105">Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse トレース ソースを使用する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="0ee52-105">You use Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse trace source for [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="0ee52-106">WCF トレースは、System.ServiceModel をという名前のソースに書き込まれます。</span><span class="sxs-lookup"><span data-stu-id="0ee52-106">WCF traces are written to the source named System.ServiceModel.</span></span>  
  
 <span data-ttu-id="0ee52-107">アダプター開発者は、Microsoft.ServiceModel.Channels.Common.AdapterTrace クラスを使用してアダプターのトレース ソース名を提供できます。</span><span class="sxs-lookup"><span data-stu-id="0ee52-107">The adapter developer can provide a trace source name for the adapter using Microsoft.ServiceModel.Channels.Common.AdapterTrace class.</span></span> <span data-ttu-id="0ee52-108">[!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]アダプター開発者によっては、アダプター コード内の実装を提供するために使用するトレース ラッパー クラスを生成します。</span><span class="sxs-lookup"><span data-stu-id="0ee52-108">The [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)] generates a trace wrapper class that can be used by the adapter developer to provide instrumentation in the adapter code.</span></span>  
  
 <span data-ttu-id="0ee52-109">WCF トレースの概要については、次を参照してください。[トレース](https://msdn.microsoft.com/library/ms730342.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="0ee52-109">For information about WCF tracing, see [Tracing](https://msdn.microsoft.com/library/ms730342.aspx).</span></span>
  
 <span data-ttu-id="0ee52-110">WCF でのトレースを分析する方法については、次を参照してください。[サービス トレース ビューアー ツール (SvcTraceViewer.exe)](https://msdn.microsoft.com/library/ms732023.aspx)です。</span><span class="sxs-lookup"><span data-stu-id="0ee52-110">For information about analyzing traces in WCF, see [Service Trace Viewer Tool (SvcTraceViewer.exe)](https://msdn.microsoft.com/library/ms732023.aspx).</span></span> 
  
## <a name="sample-trace-wrapper-utility-class"></a><span data-ttu-id="0ee52-111">サンプルのトレース ラッパーのユーティリティ クラス</span><span class="sxs-lookup"><span data-stu-id="0ee52-111">Sample Trace Wrapper Utility Class</span></span>  
  
```  
public class EchoAdapterUtilities  
{  
    static AdapterTrace trace = new AdapterTrace("Microsoft.Adapters.Samples.Echo.EchoAdapter");  
  
    /// <summary>  
    /// Gets the AdapterTrace  
    /// </summary>  
    public static AdapterTrace Trace  
    {  
        get  
        {  
            return trace;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="0ee52-112">以前のユーティリティ クラスは、アダプターのコンシューマーのインストルメンテーション データを提供するアダプター コード全体で、アダプター開発者によって使用できます。</span><span class="sxs-lookup"><span data-stu-id="0ee52-112">The previous utility class can then be used by the adapter developer throughout the adapter code to provide instrumentation data for the adapter consumers.</span></span>  
  
 <span data-ttu-id="0ee52-113">EchoAdapterUtilities.Trace.Trace (System.Diagnostics.TraceEventType.Information、"EchoAdapterConnection::Open"、「接続が正常に開かれた!」) です。</span><span class="sxs-lookup"><span data-stu-id="0ee52-113">EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully opened!");</span></span>  
  
## <a name="enable-tracing-for-the-adapter-and-wcf-lob-adapter-sdk-runtime"></a><span data-ttu-id="0ee52-114">アダプターと WCF LOB アダプター SDK ランタイムに対してトレースを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0ee52-114">Enable Tracing for the Adapter and WCF LOB Adapter SDK Runtime</span></span>  
 <span data-ttu-id="0ee52-115">提供されるトレースを有効にすることができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]アダプターを使用して、アプリケーションの app.config ファイルで、次のセクションを追加しています。</span><span class="sxs-lookup"><span data-stu-id="0ee52-115">You can enable tracing provided in the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] by adding the following section in the app.config file of the application using the adapter.</span></span>  
  
```  
<system.diagnostics>  
  <sources>  
    <source name="Microsoft.Adapters.Samples.Echo.EchoAdapter" switchValue="Verbose">  
      <listeners>  
        <add name="xmlTrace" />  
      </listeners>  
    </source>  
    <source name="Microsoft.ServiceModel.Channels" switchValue="Verbose">  
      <listeners>  
        <add name="xmlTrace" />  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add initializeData="C:\logs\TestEchoAdapter_Browse.svclog" type="System.Diagnostics.XmlWriterTraceListener" name="xmlTrace">  
      <filter type="" />  
    </add>  
  </sharedListeners>  
  <trace autoflush="true" />  
</system.diagnostics>  
```  
  
 <span data-ttu-id="0ee52-116">Add 要素を使用すると、使用するトレース リスナーの種類と名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="0ee52-116">You can use the add element to specify the name and type of the trace listener you want to use.</span></span> <span data-ttu-id="0ee52-117">この例の構成は、リスナーを"xmlTrace"という名前されを使用する種類として標準の .NET Framework トレース リスナー (System.Diagnostics.XmlWriterTraceListener) を追加します。</span><span class="sxs-lookup"><span data-stu-id="0ee52-117">In our example configuration, we named the Listener "xmlTrace" and added the standard .NET Framework trace listener (System.Diagnostics.XmlWriterTraceListener) as the type we want to use.</span></span> <span data-ttu-id="0ee52-118">任意の数の各ソースのトレース リスナーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="0ee52-118">You can add any number of trace listeners for each source.</span></span> <span data-ttu-id="0ee52-119">たとえば、次の例でも追加しました System.Diagnostics.TextWriterTraceListener の .NET Framework トレース リスナーを使用して"textTrace"という名前の別のリスナー。</span><span class="sxs-lookup"><span data-stu-id="0ee52-119">For example, in the following examples, we also added another listener named "textTrace" that uses the .NET Framework trace listener System.Diagnostics.TextWriterTraceListener.</span></span> <span data-ttu-id="0ee52-120">トレース リスナーは、ファイルにトレースを出力、構成ファイルで、出力ファイルの場所と名前を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ee52-120">If the trace listener emits the trace to a file, you must specify the output file location and name in the configuration file.</span></span> <span data-ttu-id="0ee52-121">これは、そのリスナー initializeData をファイルの名前に設定します。</span><span class="sxs-lookup"><span data-stu-id="0ee52-121">This is done by setting initializeData to the name of the file for that listener.</span></span>  
  
## <a name="enabling-tracing-for-the-add-adapter-service-reference-plug-in"></a><span data-ttu-id="0ee52-122">トレースを有効にすると、プラグイン アダプター サービス参照の追加</span><span class="sxs-lookup"><span data-stu-id="0ee52-122">Enabling Tracing for the Add Adapter Service Reference Plug-in</span></span>  
 <span data-ttu-id="0ee52-123">Devenv.exe.config ファイルで、次のセクションを追加することでこのプラグインであるは、トレースを有効にすることができます`\Program Files (x86)\Microsoft Visual Studio\Common7\IDE`です。</span><span class="sxs-lookup"><span data-stu-id="0ee52-123">You can enable tracing for this plug-in by adding the following section in the devenv.exe.config file located in `\Program Files (x86)\Microsoft Visual Studio\Common7\IDE`.</span></span>
  
```  
<system.diagnostics>  
   <sources>  
    <source name="Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse" switchValue="Verbose, ActivityTracing">  
      <listeners>  
        <add name="textTrace"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add initializeData="C:\logs\aasr.svclog" type="System.Diagnostics.XmlWriterTraceListener" name="xmlTrace">  
      <filter type="" />  
    </add>  
    <add initializeData="C:\logs\aasr.log" type="System.Diagnostics.TextWriterTraceListener" name="textTrace">  
      <filter type="" />  
    </add>  
  </sharedListeners>  
  <trace autoflush="true" indentsize="4" />  
</system.diagnostics>  
```  
  
## <a name="enable-tracing-for-the-consume-adapter-service-add-in"></a><span data-ttu-id="0ee52-124">トレースを有効にする、アダプターを使用する追加のサービス</span><span class="sxs-lookup"><span data-stu-id="0ee52-124">Enable Tracing for the Consume Adapter Service Add-in</span></span>  
 <span data-ttu-id="0ee52-125">ある BTSNTSVC.exe.config ファイルで、次のセクションを追加することでこのアドインでのトレースを有効にすることができます`\Program Files (x86)\Microsoft BizTalk Server`です。</span><span class="sxs-lookup"><span data-stu-id="0ee52-125">You can enable tracing for this add-in by adding the following section in the BTSNTSVC.exe.config file located in `\Program Files (x86)\Microsoft BizTalk Server`.</span></span>  
  
```  
<system.diagnostics>  
   <sources>  
    <source name="Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse" switchValue="Verbose, ActivityTracing">  
      <listeners>  
        <add name="textTrace"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add initializeData="C:\logs\aasr.svclog" type="System.Diagnostics.XmlWriterTraceListener" name="xmlTrace">  
      <filter type="" />  
    </add>  
    <add initializeData="C:\logs\aasr.log" type="System.Diagnostics.TextWriterTraceListener" name="textTrace">  
      <filter type="" />  
    </add>  
  </sharedListeners>  
  <trace autoflush="true" indentsize="4" />  
</system.diagnostics>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0ee52-126">参照</span><span class="sxs-lookup"><span data-stu-id="0ee52-126">See Also</span></span>  
 [<span data-ttu-id="0ee52-127">WCF LOB Adapter SDK を使用して作成されたアダプターをトラブルシューティングします。</span><span class="sxs-lookup"><span data-stu-id="0ee52-127">Troubleshoot adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)