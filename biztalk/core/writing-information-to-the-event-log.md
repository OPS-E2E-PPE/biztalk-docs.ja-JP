---
title: イベント ログに情報を書き込む |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d7398dc-29d8-4a7a-bab4-c8f128b47dca
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae31f6c09e8ffaeb562aa5bd5380dd533173cad0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261991"
---
# <a name="writing-information-to-the-event-log"></a>イベント ログに情報を書き込む
既定のアプリケーション ログまたはカスタム イベント ログに情報を記述することで、BizTalk アプリケーション内のさまざまなビジネス プロセスの進行状況を監視することがあります。 イベント ログへの書き込みは、次のシナリオで役立ちます。  
  
-   Windows によって提供されるツールを使用して標準的な方法でアプリケーション メッセージにアクセスするには。  
  
-   完全な履歴用のサーバー環境から他のメッセージと情報をアーカイブするには。  
  
-   イベント ログと対話するためのツールを使用してアプリケーションを監視する機能を必要とします。  
  
> [!NOTE]
>  System.Diagnostics.EventLog.WriteEntry メソッドには、メッセージ文字列のサイズ制限があります。 メッセージ文字列が 32,766 バイトを超える場合、例外を受け取ります。  
  
## <a name="writing-to-the-application-log"></a>アプリケーション ログへの書き込み  
 使用して、コードからアプリケーション ログまたは他のログを記述することができます**System.Diagnostics.EventLog**次に示すようにします。  
  
```  
System.Diagnostics.EventLog.WriteEntry("Orchestration Debug", System.String.Format("The Value = {0}", iResult));  
```  
  
 同様に、行うこともできます、  
  
```  
EventLog appLog = new EventLog();   
appLog.Source = "This Application's Name";  
appLog.WriteEntry("An entry to the Application event log.");  
```  
  
 使用する必要がある、カスタム ログを使用している場合、 **SourceExists**を記述する前にいることを確認するメソッドが存在します。  
  
## <a name="writing-to-a-custom-log"></a>カスタム ログへの書き込み  
 カスタム ログへの書き込みは、カスタム ログを作成する必要がありますまず例外とアプリケーション ログへの書き込みに似ています。 カスタム ログを作成するコードは簡単です。  
  
```  
// Create the source, if it does not already exist. if(!EventLog.SourceExists("MySource"))   
{   
  //An event log source should not be created and immediately used.  
  //There is a latency time to enable the source, it should be created  
  //prior to executing the application that uses the source.  
  EventLog.CreateEventSource("MySource", "MyNewLog");  
}  
```  
  
 ただし、ことを想定しないでください、コードが新しいイベント ログを作成するセキュリティ特権を持つアカウントで実行されることです。 イベント ログを作成して、管理者特権を受け取り、別のユーティリティ プログラムで、またはできれば .msi のインストールの一部として行う必要があります。 エクスポートされた .msi のインストールでカスタム スクリプトの使用に関する詳細については、次を参照してください。[アプリケーション展開のカスタマイズを前処理および後処理のスクリプトを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)します。