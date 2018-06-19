---
title: 外部アセンブリを使用するスクリプト |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, warnings
- Scripting functoids, external assemblies
ms.assetid: 0bdf6adc-91b9-462e-8fd0-9cb48bfa7817
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 475a3b9781eecb0ccc79165bbe54e6dfd542ecfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269202"
---
# <a name="scripting-using-external-assemblies"></a>外部アセンブリを使用するスクリプト
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でスクリプトを使用する場合は、外部アセンブリを使ったスクリプトをお勧めします。 外部アセンブリは、いくつかの利点を提供します。  
  
-   コードを簡単に共有できる  
  
-   保守が簡単である  
  
-   デバッグが簡単である  
  
> [!NOTE]
>  場合、マップのテストが失敗した、**スクリプト**functoid が GAC に登録されていない外部アセンブリを使用します。 正しく機能させるためには、外部アセンブリが、(ビルド後に配置される) 現在のプロジェクトのアセンブリと同じ bin フォルダーに格納されている必要があります。  
  
 設定スクリプトの再利用のみが必要です、**スクリプト**のプロパティ、**スクリプト**functoid です。 スクリプトはマップの外部に格納されるため、マップを変更することなくスクリプトを変更できます。 また、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] デバッグ ツールの全機能を使用して、スクリプトが正常に実行されることを確認できます。  
  
> [!WARNING]
>  外部アセンブリのコードは、スレッド セーフであることが必要です。 ストレス条件下では、マップの複数のインスタンスが同時に実行される場合があります。  
  
 サンプル関数の外部アセンブリに格納されていた場合、次を参照してください。 [XML ツール (BizTalk Server Samples フォルダ)](../core/xml-tools-biztalk-server-samples-folder.md)です。  
  
## <a name="see-also"></a>参照  
 [スクリプト Functoid](../core/scripting-functoid.md)   
 [インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)   
 [スクリプトを使用してインライン XSLT および XSLT 呼び出しテンプレート](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [スクリプト Functoid をマップに追加する方法](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [スクリプト Functoid を構成する方法](../core/how-to-configure-the-scripting-functoid.md)