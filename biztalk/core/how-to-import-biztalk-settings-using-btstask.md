---
title: インポートまたは BTSTask を使用して BizTalk の設定のエクスポート |Microsoft Docs
description: ImportSettings または ExportSettings BTSTask コマンドを使用して環境から BizTalk Server 内の別の設定を移動します。
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e3fdd8c9-3534-4c11-8acc-6cb6f5bf0989
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19143ff1f5da248b3924ce87d7dc2e686bdd80d3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384964"
---
# <a name="use-btstask-to-import-or-export-biztalk-settings"></a>BTSTask を使用して、インポートまたは BizTalk の設定をエクスポートするには

## <a name="overview"></a>概要
BTSTask コマンド ライン ユーティリティを使用してから、設定をエクスポートすることができます、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境別にインポートすることと[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]環境では、全体的なソリューションに時間が減少します。 これは、管理者が調整しようとした位置のシナリオで特に役立ちます[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]パフォーマンス、運用環境に設定をインポートできます、ステージング環境では、目的の結果を実現するために、します。 

このトピックでは、インポートまたはを使用して 1 つの環境から BizTalk Server 設定をエクスポートする手順を示します**BTSTask.exe**します。  


## <a name="import-biztalk-settings"></a>BizTalk の設定のインポート 
> [!IMPORTANT]
>  特定の環境から BizTalk 設定をインポートするには、必要がありますが既にエクスポートして XML ファイルにこれらの設定を保存します。 設定のエクスポートの詳細については、次を参照してください。[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)または**BTSTask を使用して BizTalk の設定のエクスポート**(」を参照)。  
  
 XML ファイルをインポートすることによって、ターゲット コンピューターで必要な BizTalk Server 設定をレプリケートできます。 使用して、 **BTSTask.exe**グループ、ホスト、およびホスト インスタンスの設定をインポートし、そのプロパティを相互にマップします。 以下は、設定をインポートするための必要な前提条件です。  
  
-   同様のトポロジ間で BizTalk Server 設定をインポートすることができます。  
  
-   送信先の対応するソース ホストとホスト インスタンスにマップできる必要があります。  
  
-   移行先の環境に似たハードウェア (同じ) かソース環境。 これは、基になるハードウェアに依存して、設定の一部は非常に重要です。  
  
### <a name="importsettings-command"></a>ImportSettings コマンド 
 使用することができます、 **ImportSettings**ソース環境から送信先の環境に BizTalk Server の設定をインポートする BTSTask コマンド。 参照してください[ImportSettings コマンド](../core/importsettings-command.md)に関する特定の詳細。  
  
 移行先ホストにソース ホストまたはソース ホストのインスタンスから示すように、宛先ホスト インスタンスへのマッピングを定義できます。  
  
```  
<?xml version="1.0" encoding="utf-8" ?>   
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SettingsMap>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <HostMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="BizTalkServerApplication">  
  <DestinationHosts>BizTalkServerApplication</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="BizTalkServerIsolatedHost">  
  <DestinationHosts>BizTalkServerIsolatedHost</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="Host1">  
  <DestinationHosts>Host2</DestinationHosts>   
  </SourceHost>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHost Name="Host2">  
  <DestinationHosts>Host1;Host3;Host4;Host5</DestinationHosts>   
  </SourceHost>  
  </HostMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <HostInstanceMappings>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHostInstance Name="BizTalkServerApplication:COMPUTER_NAME1">  
  <DestinationHostInstances>BizTalkServerApplication:COMPUTER_NAME2</DestinationHostInstances>   
  </SourceHostInstance>  
 HYPERLINK "file:///C:\\Users\\v-dhgunt\\AppData\\Local\\Microsoft\\Windows\\Temporary%20Internet%20Files\\Content.Outlook\\05083AAB\\ImportMap_PosScenario.xml" - <SourceHostInstance Name="Host1:COMPUTER_NAME1">  
  <DestinationHostInstances>Host2:COMPUTER_NAME2;Host3:COMPUTER_NAME3;Host4:COMPUTER_NAME4;Host5:COMPUTER_NAME5</DestinationHostInstances>   
  </SourceHostInstance>  
  </HostInstanceMappings>  
  </SettingsMap>  
  
```  
  
 マップ ファイルの場合は、"hostname:machinename"のホスト インスタンスを入力します。 例 :"Host1:Server1"ホスト"Host1 が実行されている (または提示) コンピューターのインスタンスを意味する ' Server1"。  
  
 1: n のソース宛先へのマッピングからを入力するには、セミコロンで区切ったリストを使用します。 例 :  
  
```  
SourceHost Name="SourceHost1"   
......DestinationHosts   
............DestHost1;DestHost2;DestHost3   
....../DestinationHosts   
/SourceHost  
```  
  
 対応するホスト マッピングも作成され、ホストのインスタンスのみをマップできます。 SourceHost1"は、ホスト マッピングで DestinationHost1"にマップされているが場合、DestinationHost1 のインスタンス (ある場合) が SourceHost1"のインスタンス (ある場合) にのみマップできます。 この制約の UI のインポート ウィザードによって行われます。 マップ ファイルで明示的に記述する必要があります。  


## <a name="export-biztalk-settings"></a>BizTalk 設定をエクスポートします。  

複数の BizTalk 設定をエクスポートする方法があります。 

1. 使用して、 **ExportSettings**ソース環境の BizTalk Server 設定を XML ファイルにエクスポートに BTSTask コマンド。 参照してください[ExportSettings コマンド](../core/exportsettings-command.md)の詳細。  

2.  BizTalk Server 管理の設定ダッシュ ボードを使用します。 参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)手順については、します。

 
> [!TIP]
>  XML ファイルに BizTalk Server の設定がターゲット環境に適用する方法については、次を参照してください。[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)します。 
  
## <a name="see-also"></a>参照  
 [BizTalk Server パフォーマンス チューニングの自動化](../core/automating-biztalk-server-performance-tuning.md)