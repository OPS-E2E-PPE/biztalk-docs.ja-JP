---
title: BTSNTSvc.exe.config ファイル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f2bb89a7-4fff-4ccf-a0a7-20ca610f2ddf
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c8347f7027371cd77c5b712ed3e12380e30bc34
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357998"
---
# <a name="btsntsvcexeconfig-file"></a>BTSNTSvc.exe.config File
退避プロパティとその既定値は構成可能で[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]または BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) で XML として。 BizTalk 構成ファイルの値が先に適用されます。 次に、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] の設定が適用されます。 退避プロパティは、オーケストレーションを含んでいるすべてのホスト インスタンスの開始時に読み取られます。  
  
 このトピックでは、BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) について説明します。 多くの退避プロパティは表示されません。 これらのプロパティおよび既定値は、構成ファイルで明示的に指定されていない場合でも常に適用されています。  
  
 既定値を変更するにする必要があります明示的に追加、構成ファイルをします。 既定の退避動作を変更する方法については、次を参照してください。[オーケストレーション制限の設定の変更方法](../core/how-to-modify-orchestration-throttling-settings.md)します。 オーケストレーション メモリ制限については、次を参照してください。[オーケストレーション メモリ制限の設定の変更方法](../core/how-to-modify-orchestration-memory-throttling-settings.md)します。  
  
 BTSNTSvc.exe.config ファイルの内容を次に示します。 このファイルは常に BTSNTSvc.exe ファイル、通常は C:\Program files \microsoft BizTalk Server と同じディレクトリ内にあります。  
  
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
 [BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)