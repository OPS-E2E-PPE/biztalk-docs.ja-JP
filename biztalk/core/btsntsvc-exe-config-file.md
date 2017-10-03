---
title: "BTSNTSvc.exe.config ファイル |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2bb89a7-4fff-4ccf-a0a7-20ca610f2ddf
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 303924e2aaf8304388a18d2ffe70d99fdc69acd3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="btsntsvcexeconfig-file"></a>BTSNTSvc.exe.config ファイル
退避プロパティとその既定値は、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] を使用するか、または XML として BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) で構成可能です。 BizTalk 構成ファイルの値が先に適用されます。 次に、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] の設定が適用されます。 退避プロパティは、オーケストレーションを含んでいるすべてのホスト インスタンスの開始時に読み取られます。  
  
 このトピックでは、BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) について説明します。 多くの退避プロパティはリストされません。 これらのプロパティおよび既定値は、構成ファイルで明示的に指定されていない場合でも常に適用されています。  
  
 既定値を変更するには、構成ファイルに明示的に追加する必要があります。 既定の退避動作を変更する方法については、次を参照してください。[オーケストレーション制限の設定の変更方法](../core/how-to-modify-orchestration-throttling-settings.md)です。 オーケストレーション メモリの制限については、次を参照してください。[オーケストレーション メモリ制限の設定の変更方法](../core/how-to-modify-orchestration-memory-throttling-settings.md)です。  
  
 BTSNTSvc.exe.config ファイルの内容を以下に示します。 このファイルは常に BTSNTSvc.exe ファイルと同じディレクトリ (通常は C:\Program Files\Microsoft [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]) に配置されます。  
  
```  
<?xml version="1.0" ?>  
<configuration>  
       <configSections>  
              <section name="xlangs" type="Microsoft.XLANGs.BizTalk.CrossProcess.XmlSerializationConfigurationSectionHandler, Microsoft.XLANGs.BizTalk.CrossProcess" />  
       </configSections>  
       <runtime>  
              <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
                     <probing privatePath="BizTalk Assemblies;Developer Tools;Tracking" />  
              </assemblyBinding>  
       </runtime>  
       <xlangs>  
              <Configuration>  
                     <Dehydration MaxThreshold="1800" MinThreshold="1" ConstantThreshold="-1">  
                            <VirtualMemoryThrottlingCriteria OptimalUsage="900" MaximalUsage="1300" IsActive="true" />  
                            <PrivateMemoryThrottlingCriteria OptimalUsage="50" MaximalUsage="350" IsActive="true" />  
                            <PhysicalMemoryThrottlingCriteria OptimalUsage="50" MaximalUsage="350" IsActive="false" />  
                     </Dehydration>  
              </Configuration>  
       </xlangs>  
</configuration>  
```  
  
## <a name="see-also"></a>参照  
 [BizTalk server 設定ダッシュ ボードを使用してパフォーマンス チューニング](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)