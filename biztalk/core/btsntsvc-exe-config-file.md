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
# <a name="btsntsvcexeconfig-file"></a><span data-ttu-id="04a39-102">BTSNTSvc.exe.config File</span><span class="sxs-lookup"><span data-stu-id="04a39-102">BTSNTSvc.exe.config File</span></span>
<span data-ttu-id="04a39-103">退避プロパティとその既定値は構成可能で[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)]または BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) で XML として。</span><span class="sxs-lookup"><span data-stu-id="04a39-103">Dehydration properties and their default values are configurable in [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] or as XML in the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="04a39-104">BizTalk 構成ファイルの値が先に適用されます。</span><span class="sxs-lookup"><span data-stu-id="04a39-104">The values in the BizTalk configuration file are applied first.</span></span> <span data-ttu-id="04a39-105">次に、[!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] の設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="04a39-105">Then, the [!INCLUDE[btsSettingsDashboard](../includes/btssettingsdashboard-md.md)] settings are applied.</span></span> <span data-ttu-id="04a39-106">退避プロパティは、オーケストレーションを含んでいるすべてのホスト インスタンスの開始時に読み取られます。</span><span class="sxs-lookup"><span data-stu-id="04a39-106">The dehydration properties are read when all host instances containing an orchestration start.</span></span>  
  
 <span data-ttu-id="04a39-107">このトピックでは、BizTalk 構成ファイル (BTSNTSvc.exe.config または BTSNTSvc64.exe.config) について説明します。</span><span class="sxs-lookup"><span data-stu-id="04a39-107">This topic focuses on the BizTalk configuration file (BTSNTSvc.exe.config or BTSNTSvc64.exe.config).</span></span> <span data-ttu-id="04a39-108">多くの退避プロパティは表示されません。</span><span class="sxs-lookup"><span data-stu-id="04a39-108">Many dehydration properties are not listed.</span></span> <span data-ttu-id="04a39-109">これらのプロパティおよび既定値は、構成ファイルで明示的に指定されていない場合でも常に適用されています。</span><span class="sxs-lookup"><span data-stu-id="04a39-109">These properties and their default values are still applied, even if they are not explicitly specified in the configuration file.</span></span>  
  
 <span data-ttu-id="04a39-110">既定値を変更するにする必要があります明示的に追加、構成ファイルをします。</span><span class="sxs-lookup"><span data-stu-id="04a39-110">To change the default values, you must explicitly add them to your configuration file.</span></span> <span data-ttu-id="04a39-111">既定の退避動作を変更する方法については、次を参照してください。[オーケストレーション制限の設定の変更方法](../core/how-to-modify-orchestration-throttling-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="04a39-111">For information about how to change the default dehydration behavior, see [How to Modify Orchestration Throttling Settings](../core/how-to-modify-orchestration-throttling-settings.md).</span></span> <span data-ttu-id="04a39-112">オーケストレーション メモリ制限については、次を参照してください。[オーケストレーション メモリ制限の設定の変更方法](../core/how-to-modify-orchestration-memory-throttling-settings.md)します。</span><span class="sxs-lookup"><span data-stu-id="04a39-112">For information about orchestration memory throttling, see [How to Modify Orchestration Memory Throttling Settings](../core/how-to-modify-orchestration-memory-throttling-settings.md).</span></span>  
  
 <span data-ttu-id="04a39-113">BTSNTSvc.exe.config ファイルの内容を次に示します。</span><span class="sxs-lookup"><span data-stu-id="04a39-113">Following is the contents of the BTSNTSvc.exe.config file.</span></span> <span data-ttu-id="04a39-114">このファイルは常に BTSNTSvc.exe ファイル、通常は C:\Program files \microsoft BizTalk Server と同じディレクトリ内にあります。</span><span class="sxs-lookup"><span data-stu-id="04a39-114">This file is always located in the same directory as the BTSNTSvc.exe file, which is usually C:\Program Files\Microsoft BizTalk Server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="04a39-115">参照</span><span class="sxs-lookup"><span data-stu-id="04a39-115">See Also</span></span>  
 [<span data-ttu-id="04a39-116">BizTalk Server パフォーマンス チューニングのための設定ダッシュボードの使用</span><span class="sxs-lookup"><span data-stu-id="04a39-116">Using Settings Dashboard for BizTalk Server Performance Tuning</span></span>](../core/using-settings-dashboard-for-biztalk-server-performance-tuning.md)