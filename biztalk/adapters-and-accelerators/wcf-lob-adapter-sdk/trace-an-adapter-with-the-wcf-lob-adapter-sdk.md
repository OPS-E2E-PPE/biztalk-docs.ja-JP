---
title: "WCF LOB Adapter SDK を持つアダプターのトレース |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7a4f4758-3e3e-48c4-b4cf-414c2b05d539
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ca4b68f23f791de3ecd68bc69b85c2908b6d7a0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="trace-an-adapter-with-the-wcf-lob-adapter-sdk"></a>WCF LOB Adapter SDK を持つアダプターをトレースします。
[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]トレースは、Systems.Diagnostics 上に作成されています。 Microsoft.ServiceModel.Channels トレース ソースを使用する、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]ランタイム。  Microsoft.ServiceModel.Channels.Tools.MetadataSearchBrowse トレース ソースを使用する[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]と[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]です。 WCF トレースは、System.ServiceModel をという名前のソースに書き込まれます。  
  
 アダプター開発者は、Microsoft.ServiceModel.Channels.Common.AdapterTrace クラスを使用してアダプターのトレース ソース名を提供できます。 [!INCLUDE[afdevwizardnameshort](../../includes/afdevwizardnameshort-md.md)]アダプター開発者によっては、アダプター コード内の実装を提供するために使用するトレース ラッパー クラスを生成します。  
  
 WCF トレースの概要については、次を参照してください。[トレース](https://msdn.microsoft.com/library/ms730342.aspx)です。
  
 WCF でのトレースを分析する方法については、次を参照してください。[サービス トレース ビューアー ツール (SvcTraceViewer.exe)](https://msdn.microsoft.com/library/ms732023.aspx)です。 
  
## <a name="sample-trace-wrapper-utility-class"></a>サンプルのトレース ラッパーのユーティリティ クラス  
  
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
  
 以前のユーティリティ クラスは、アダプターのコンシューマーのインストルメンテーション データを提供するアダプター コード全体で、アダプター開発者によって使用できます。  
  
 EchoAdapterUtilities.Trace.Trace (System.Diagnostics.TraceEventType.Information、"EchoAdapterConnection::Open"、「接続が正常に開かれた!」) です。  
  
## <a name="enable-tracing-for-the-adapter-and-wcf-lob-adapter-sdk-runtime"></a>アダプターと WCF LOB アダプター SDK ランタイムに対してトレースを有効にします。  
 提供されるトレースを有効にすることができます、[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]アダプターを使用して、アプリケーションの app.config ファイルで、次のセクションを追加しています。  
  
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
  
 Add 要素を使用すると、使用するトレース リスナーの種類と名前を指定します。 この例の構成は、リスナーを"xmlTrace"という名前されを使用する種類として標準の .NET Framework トレース リスナー (System.Diagnostics.XmlWriterTraceListener) を追加します。 任意の数の各ソースのトレース リスナーを追加することができます。 たとえば、次の例でも追加しました System.Diagnostics.TextWriterTraceListener の .NET Framework トレース リスナーを使用して"textTrace"という名前の別のリスナー。 トレース リスナーは、ファイルにトレースを出力、構成ファイルで、出力ファイルの場所と名前を指定する必要があります。 これは、そのリスナー initializeData をファイルの名前に設定します。  
  
## <a name="enabling-tracing-for-the-add-adapter-service-reference-plug-in"></a>トレースを有効にすると、プラグイン アダプター サービス参照の追加  
 Devenv.exe.config ファイルで、次のセクションを追加することでこのプラグインであるは、トレースを有効にすることができます`\Program Files (x86)\Microsoft Visual Studio\Common7\IDE`です。
  
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
 ある BTSNTSVC.exe.config ファイルで、次のセクションを追加することでこのアドインでのトレースを有効にすることができます`\Program Files (x86)\Microsoft BizTalk Server`です。  
  
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