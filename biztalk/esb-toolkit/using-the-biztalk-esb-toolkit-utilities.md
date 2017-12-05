---
title: "BizTalk ESB Toolkit ユーティリティを使用して |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2dc05ac-831a-44e1-bd44-e41398552ab1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db4a8ef2def05e0b77d272463d7a79f937623b1a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-biztalk-esb-toolkit-utilities"></a>BizTalk ESB Toolkit ユーティリティを使用します。
このセクションの一部として含まれているさまざまなユーティリティの説明、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]です。  
  
 **ESB Itinerary インポート ユーティリティ**  
  
 このユーティリティは、\bin ディレクトリの下にある、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] EsbImportUtil.exe という名前です。 このユーティリティを使用して、発行または ESBItineraryDB データベースに XML 旅程をデプロイすることができます。  
  
 ユーティリティの構文は次のとおりです。  
  
```  
>EsbImportUtil <Parameter1> <Value> <parameter2> <Value>...  
```  
  
 さまざまなパラメーターを受け入れる次に示します。  
  
 /?:\<パラメーターのヘルプを表示します。\>  
  
 /f:\<行程 xml ファイルのパス\>  
  
 展開/c\<発行 &#124; 展開\>  
  
 /n:\<行程の既定の名前\>  
  
 /v:\<行程の既定のバージョン ('<major.minor' の形式)\>  
  
 /o:\<サイレントの上書き\>  
  
 このユーティリティを使用する方法の例を次に示します。  
  
 行程データベースに発行します。  
  
```  
>EsbImportUtil /f:myitinerary.xml /c:published  
```  
  
 行程データベースを展開します。  
  
```  
>EsbImportUtil  /f:myitinerary.xml /c:deployed  
```  
  
 **SSO の構成ユーティリティを永続化します。**  
  
 このユーティリティは、\bin ディレクトリの下にある、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Microsoft.Practices.ESB.PersistConfigurationTool.exe という名前です。 このユーティリティを使用して、BizTalk SSO データベースに ESB の構成情報を保持することができます。 これは、構成情報を表示および SSO データベースから構成情報を削除するも使用できます。  
  
 ユーティリティの構文は次のとおりです。  
  
 **構成セクションを追加します。**  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /P /F:app.config /S:SectionName /A:ApplicationName  
```  
  
> [!NOTE]
>  /S が指定されていない場合は、以下のセクションが追加されます: connectionStrings、esb、esb.resolver および cachingConfiguration です。  
  
 **セクションを削除します。**  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /R /S:SectionName  
```  
  
 既存のセクションを表示するには、/V スイッチを使用してアプリケーションとセクション スイッチを使用します。  
  
 管理者グループ名を設定するには、AG:AdminGroupName スイッチを使用します。  
  
 ユーザー グループ名を設定するには、UG:UserGroupName スイッチを使用します。