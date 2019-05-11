---
title: 外部アセンブリを使用したスクリプト |Microsoft Docs
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
ms.openlocfilehash: 4876d0b7c236be890649e5050b09e538b07742a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395524"
---
# <a name="scripting-using-external-assemblies"></a>外部アセンブリを使用するスクリプト
外部アセンブリを使用したスクリプトは、Microsoft でスクリプトを使用することをお勧め[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 外部アセンブリは、いくつかの利点を提供します。  
  
-   簡単なコードの共有  
  
-   保守が簡単  
  
-   デバッグの簡略化  
  
> [!NOTE]
>  場合、マップのテストが失敗した、 **Scripting** functoid は、GAC に登録されていない外部アセンブリを使用します。 場合、外部のアセンブリを (ビルド後に配置されます) 現在のプロジェクトのアセンブリと同じ bin フォルダーで動作します。  
  
 設定スクリプトの再利用のみが必要です、**スクリプト**のプロパティ、 **Scripting** functoid。 スクリプトで、マップの外部であるため、マップを変更することがなくスクリプトを変更することができます。 すべての配列を使用して[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]デバッグ ツール、スクリプトの確認が正常に実行されます。  
  
> [!WARNING]
>  外部アセンブリ内のコードは、スレッド セーフである必要があります。 ストレス条件下で、マップの複数のインスタンスを同時に実行される可能性があります。  
  
 サンプル関数の外部アセンブリに格納されている場合、次を参照してください。 [XML ツール (BizTalk Server Samples フォルダー)](../core/xml-tools-biztalk-server-samples-folder.md)します。  
  
## <a name="see-also"></a>参照  
 [スクリプト Functoid](../core/scripting-functoid.md)   
 [インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)   
 [使用してインライン XSLT および XSLT 呼び出しテンプレート スクリプト](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)   
 [マップにスクリプト Functoid を追加する方法](../core/how-to-add-scripting-functoids-to-a-map.md)   
 [スクリプト Functoid の構成方法](../core/how-to-configure-the-scripting-functoid.md)