---
title: WCF LOB Adapter SDK のアダプターのトレース |Microsoft Docs
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
ms.openlocfilehash: b03e56127071215a33b81f1d16ad653a9764d1d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65363170"
---
# <a name="trace-an-adapter-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK のアダプターをトレースします。
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] トレースは、Systems.Diagnostics 上に構築されます。 Microsoft.ServiceModel.Channels のトレース ソースを使用して、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム。  Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse のトレース ソースを使用する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]します。 WCF トレースは、System.ServiceModel をという名前のソースに書き込まれます。  
  
 アダプター開発者は、Microsoft.ServiceModel.Channels.Common.AdapterTrace クラスを使用して、アダプターのトレース ソース名を提供できます。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]アダプター開発者によって、アダプター コード内のインストルメンテーションを提供するのに使用できるトレース ラッパー クラスを生成します。  
  
 WCF トレースについては、次を参照してください。[トレース](https://msdn.microsoft.com/library/ms730342.aspx)します。
  
 WCF でのトレースを分析する方法の詳細については、次を参照してください。[サービス トレース ビューアー ツール (SvcTraceViewer.exe)](https://msdn.microsoft.com/library/ms732023.aspx)します。 
  
## <a name="sample-trace-wrapper-utility-class"></a>サンプル トレース ラッパー ユーティリティ クラス  
  
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
  
 前のユーティリティ クラスは、アダプターのコンシューマー向けのインストルメンテーション データを提供するアダプター コード全体で、アダプター開発者によって使用できます。  
  
 EchoAdapterUtilities.Trace.Trace(System.Diagnostics.TraceEventType.Information, "EchoAdapterConnection::Open", "Connection successfully opened!");  
  
## <a name="enable-tracing-for-the-adapter-and-wcf-lob-adapter-sdk-runtime"></a>アダプターと WCF LOB アダプター SDK ランタイム トレースを有効にします。  
 提供されるトレースを有効にすることができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]アダプターを使用してアプリケーションの app.config ファイルで、次のセクションを追加します。  
  
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
  
 使用するトレース リスナーの種類と名前を指定するのに追加要素を使用することができます。 この例の構成は、という名前のリスナー"xmlTrace"しを使用する型として標準の .NET Framework トレース リスナー (System.Diagnostics.XmlWriterTraceListener) を追加します。 任意の数の各ソースのトレース リスナーを追加することができます。 たとえば、次の例でも追加しました System.Diagnostics.TextWriterTraceListener の .NET Framework トレース リスナーを使用して"textTrace"という名前の別のリスナー。 ファイルにトレースを出力するトレース リスナーに、構成ファイルで、出力ファイルの場所と名前を指定する必要があります。 これは、ファイルの名前をリスナーの initializeData に設定します。  
  
## <a name="enabling-tracing-for-the-add-adapter-service-reference-plug-in"></a>トレースを有効にすると、プラグインのアダプター サービス参照の追加  
 Devenv.exe.config ファイルで、次のセクションを追加することでこのプラグインであるは、トレースを有効にすることができます`\Program Files (x86)\Microsoft Visual Studio\Common7\IDE`します。
  
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
  
## <a name="enable-tracing-for-the-consume-adapter-service-add-in"></a>トレースを有効にする、アダプターを使用する追加のサービス  
 ある BTSNTSVC.exe.config ファイルで、次のセクションを追加することでこのアドインでのトレースを有効にすることができます`\Program Files (x86)\Microsoft BizTalk Server`します。  
  
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
  
## <a name="see-also"></a>参照  
 [WCF LOB Adapter SDK を使用して作成されたアダプターをトラブルシューティングします。](../../adapters-and-accelerators/wcf-lob-adapter-sdk/troubleshoot-adapter-created-using-the-wcf-lob-adapter-sdk.md)