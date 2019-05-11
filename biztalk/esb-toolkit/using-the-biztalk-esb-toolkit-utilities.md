---
title: BizTalk ESB Toolkit ユーティリティを使用する |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2dc05ac-831a-44e1-bd44-e41398552ab1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97fcea7d2d7818b59ffae75754d04f5102e5f91c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396423"
---
# <a name="using-the-biztalk-esb-toolkit-utilities"></a>BizTalk ESB Toolkit ユーティリティを使用します。
このセクションの一部として含まれているさまざまなユーティリティの説明、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]します。  
  
 **ESB スケジュール オンランプ Import ユーティリティ**  
  
 このユーティリティが \bin ディレクトリの下にある、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] EsbImportUtil.exe という名前です。 このユーティリティは、発行またはデプロイ ESBItineraryDB データベースに旅行プラン XML を使用できます。  
  
 ユーティリティの構文は次のとおりです。  
  
```  
>EsbImportUtil <Parameter1> <Value> <parameter2> <Value>...  
```  
  
 次に示します、さまざまなパラメーターを受け入れることができます。  
  
 /?:\<パラメーターのヘルプを表示します。\>  
  
 /f:\<スケジュール オンランプ xml ファイルのパス\>  
  
 c:\<発行&#124;展開\>  
  
 /n:\<既定のスケジュール名\>  
  
 /v:\<既定のスケジュールのバージョン ('major.minor' 形式)\>  
  
 /o:\<サイレントの上書き\>  
  
 このユーティリティを使用する方法の例を次に示します。  
  
 行程データベースを発行します。  
  
```  
>EsbImportUtil /f:myitinerary.xml /c:published  
```  
  
 行程データベースを展開します。  
  
```  
>EsbImportUtil  /f:myitinerary.xml /c:deployed  
```  
  
 **SSO 構成ユーティリティを永続化します。**  
  
 このユーティリティが \bin ディレクトリの下にある、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] Microsoft.Practices.ESB.PersistConfigurationTool.exe という名前です。 このユーティリティは、BizTalk SSO データベースに、ESB の構成情報を永続化に使用できます。 これは、構成情報を表示および SSO データベースから構成情報を削除するも使用できます。  
  
 ユーティリティの構文は次のとおりです。  
  
 **構成セクションを追加するには。**  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /P /F:app.config /S:SectionName /A:ApplicationName  
```  
  
> [!NOTE]
>  /S が指定されていない場合、次のセクションが追加されます: connectionStrings、esb、esb.resolver および cachingConfiguration します。  
  
 **セクションを削除するには。**  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /R /S:SectionName  
```  
  
 既存のセクションを表示するには、/V スイッチを使用して、アプリケーションとセクション スイッチを使用します。  
  
 管理者グループ名を設定するには、AG:AdminGroupName スイッチを使用します。  
  
 ユーザー グループの名前を設定するには、UG:UserGroupName スイッチを使用します。