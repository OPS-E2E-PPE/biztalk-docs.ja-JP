---
title: イベント ログに情報を書き込む |Microsoft ドキュメント
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
ms.openlocfilehash: f848cafd6ee9247511db3b9a6dad7dc5da91236b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22289578"
---
# <a name="writing-information-to-the-event-log"></a>イベント ログへの情報の書き込み
既定のアプリケーション ログまたはカスタム イベント ログに情報を書き込むことで、BizTalk アプリケーション内の異なるビジネス プロセスの進捗を監視できます。 イベント ログへの書き込みは、次のようなシナリオで役に立ちます。  
  
-   Windows で提供されているツールを使用し、標準的な方法でアプリケーションのメッセージにアクセスする。  
  
-   より完全な履歴を残すために、サーバー環境からの他のメッセージと共に情報をアーカイブする。  
  
-   イベント ログと対話できるツールを使用してアプリケーションを監視する。  
  
> [!NOTE]
>  System.Diagnostics.EventLog.WriteEntry メソッドには、メッセージ文字列に関してサイズ制限があります。 メッセージ文字列が 32,766 バイトを超えると、例外が発生します。  
  
## <a name="writing-to-the-application-log"></a>アプリケーション ログへの書き込み  
 使用して、コードから、アプリケーション ログまたは他のログに記述することができます**System.Diagnostics.EventLog**次に示すようにします。  
  
```  
System.Diagnostics.EventLog.WriteEntry("Orchestration Debug", System.String.Format("The Value = {0}", iResult));  
```  
  
 同様に、次のように記述することもできます。  
  
```  
EventLog appLog = new EventLog();   
appLog.Source = "This Application's Name";  
appLog.WriteEntry("An entry to the Application event log.");  
```  
  
 使用する必要がある、カスタム ログを使用している場合、 **SourceExists**を記述する前にいることを確認するメソッドが存在します。  
  
## <a name="writing-to-a-custom-log"></a>カスタム ログへの書き込み  
 カスタム ログへの書き込みはアプリケーション ログへの書き込みと似ていますが、最初にカスタム ログを作成する必要があります。 カスタム ログは簡単なコードで作成できます。  
  
```  
// Create the source, if it does not already exist. if(!EventLog.SourceExists("MySource"))   
{   
  //An event log source should not be created and immediately used.  
  //There is a latency time to enable the source, it should be created  
  //prior to executing the application that uses the source.  
  EventLog.CreateEventSource("MySource", "MyNewLog");  
}  
```  
  
 ただし、新しいイベント ログを作成するためのセキュリティ特権を持つアカウントでコードが実行されることを前提にすることはできません。 イベント ログの作成には管理者特権が必要であり、別のユーティリティ プログラムで、またはできれば .msi インストールの一部として作成する必要があります。 エクスポートされた .msi のインストールでカスタム スクリプトを使用する方法の詳細については、次を参照してください。[前処理および後処理のスクリプトをアプリケーションの展開のカスタマイズを使用して](../core/using-pre-and-post-processing-scripts-to-customize-application-deployment.md)です。