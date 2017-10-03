---
title: "インポートまたは BTSTask を使用して BizTalk の設定をエクスポート |Microsoft ドキュメント"
description: "ImportSettings または ExportSettings BTSTask コマンドを使用して、環境から BizTalk Server 内の別の設定を移動します。"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e3fdd8c9-3534-4c11-8acc-6cb6f5bf0989
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99aecaea767133fc5f3cb77d38dc174b09733674
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="use-btstask-to-import-or-export-biztalk-settings"></a>BTSTask を使用して、インポートまたは BizTalk の設定をエクスポートするには

## <a name="overview"></a>概要
BTSTask コマンドライン ユーティリティを使用して、1 つの [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境から設定をエクスポートし、その設定を別の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境にインポートすることによって、ソリューションにかかる時間を短縮できます。 これは、管理者がステージング環境で [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のパフォーマンスを調整し、適正な結果が得られた時点で設定を実稼働環境にインポートする場合、特に役立ちます。 

このトピックの内容をインポートまたは 1 つの環境から BizTalk Server 設定を使用して別にエクスポートする手順について説明**BTSTask.exe**です。  


## <a name="import-biztalk-settings"></a>BizTalk 設定をインポートします。 
> [!IMPORTANT]
>  特定の環境から BizTalk 設定をインポートするには、その設定をエクスポートして XML ファイルに保存しておく必要があります。 設定のエクスポートの詳細については、次を参照してください。[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)または**BTSTask を使用して BizTalk の設定のエクスポート**(」を参照)。  
  
 XML ファイルをインポートすることで、対象コンピューターで必要な BizTalk Server 設定をレプリケートできます。 使用して、 **BTSTask.exe**グループ、ホスト、およびホスト インスタンス設定をインポートして、そのプロパティを相互にマップできます。 次に設定をインポートする際に必要な前提条件を示します。  
  
-   BizTalk Server 設定は同様のトポロジ間でインポートできます。  
  
-   送信元のホストとホスト インスタンスを送信先の対応するホストとホスト インスタンスにマップできる必要があります。  
  
-   インポート先環境には、インポート元環境と (同じかまたは) 似たハードウェアがあります。 一部の設定は基礎となるハードウェアに依存しているため、これは重要です。  
  
### <a name="importsettings-command"></a>ImportSettings コマンド 
 使用することができます、 **ImportSettings**を送信先の環境に、ソース環境から BizTalk Server の設定をインポートする BTSTask コマンド。 参照してください[ImportSettings コマンド](../core/importsettings-command.md)詳細です。  
  
 送信元ホストから送信先ホストおよび送信元ホスト インスタンスから送信先ホスト インスタンスへのマッピングは、次のように定義できます。  
  
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
  
 マップ ファイルには、"hostname:machinename"ホスト インスタンスを入力します。 たとえば、"Host1:Server1" は、コンピューター "Server1" で実行中の (または存在している) ホスト "Host1" を意味します。  
  
 1: n のソースを移行先のマッピングを入力するには、セミコロンで区切ったリストを使用します。 例:  
  
```  
SourceHost Name="SourceHost1"   
......DestinationHosts   
............DestHost1;DestHost2;DestHost3   
....../DestinationHosts   
/SourceHost  
```  
  
 ホスト インスタンスをマップするには、対応するホスト マッピングも作成されている必要があります。 ホスト マッピングで "SourceHost1" が "DestinationHost1" にマップされている場合、"DestinationHost1" のインスタンス (ある場合) は "SourceHost1" のインスタンス (ある場合) にのみマップできます。 この制約は UI インポート ウィザードにより処理されます。 マップ ファイルにはこのことを明示的に記述する必要があります。  


## <a name="export-biztalk-settings"></a>BizTalk 設定をエクスポートします。  

BizTalk の設定をエクスポートする方法はいくつかあります。 

1. 使用して、 **ExportSettings** XML ファイルをソース環境の BizTalk Server の設定をエクスポートする BTSTask コマンド。 参照してください[ExportSettings コマンド](../core/exportsettings-command.md)詳細についてはします。  

2.  BizTalk Server 管理コンソールで、設定ダッシュ ボードを使用します。 参照してください[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)手順については、します。

 
> [!TIP]
>  ターゲット環境に XML ファイルに BizTalk Server の設定を適用する方法については、次を参照してください。[インポートまたはエクスポート BizTalk の設定を使用して設定のダッシュ ボード](how-to-import-biztalk-settings-using-settings-dashboard.md)です。 
  
## <a name="see-also"></a>参照  
 [BizTalk Server の自動化のパフォーマンス チューニング](../core/automating-biztalk-server-performance-tuning.md)