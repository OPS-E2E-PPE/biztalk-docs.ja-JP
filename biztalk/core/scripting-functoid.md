---
title: スクリプト Functoid |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scripting functoids, about Scripting functoids
- Scripting functoids
- Scripting functoids, configuring
ms.assetid: ea8353da-049b-4e0c-a700-f51708db22a3
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72f85d7b542b8ffd6eaf4b7ab6236f11aba8a34f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395513"
---
# <a name="scripting-functoid"></a>スクリプト Functoid
**Scripting** functoid では、実行時に使用できない機能を実行するカスタム スクリプトまたはコードを使用することができます。 たとえばを使用して実行時に .NET アセンブリを呼び出すことができます、 **Scripting** functoid および独自のカスタム関数の記述。  
  
 **Scripting** functoid は、次の言語をサポートしています。  
  
- C# .NET  
  
- JScript .NET  
  
- Visual Basic .NET  
  
- Extensible Stylesheet Language Transformations (XSLT)  
  
- XSLT 呼び出しテンプレート  
  
  もう 1 つの重要な違い現在**Scripting** functoid と以前のバージョンは、スクリプトが必要されなく作成、functoid 自体に格納されています。 別の .NET アセンブリにスクリプトを作成し、使用してアセンブリを参照する代わりに、**スクリプト**プロパティ。 別のアセンブリにあるスクリプトには、1 つ以上のマップで同じスクリプトを使用することができます。 またを購入することがあります**Scripting**サード パーティ ベンダーから functoid アセンブリ。  
  
  使用することができます**Scripting** functoid を BizTalk マッパーの現在のバージョンの BizTalk マッパーの以前のバージョンで作成します。 ただし、最初に、functoid を移行する必要があります。 移行する方法の詳細についての**Scripting** functoid を参照してください[Functoid の移行](../core/migrating-functoids.md)します。  
  
  追加すると、 **Scripting**マップに functoid、functoid を使用してスクリプトを構成する必要があります。 選択した場合、 **Scripting** functoid、**スクリプト**でプロパティが有効になっている、**プロパティ**ウィンドウ。 省略記号をクリックした場合 (**.**)、このプロパティのボタン、**スクリプト Functoid の構成** ダイアログ ボックスが表示されます。 または、ダブルクリック、 **Scripting** functoid。  
  
  次の表では、このダイアログ ボックスのフィールドを示します。  
  
|スクリプト Functoid のダイアログ ボックスのフィールドを構成します。|説明|  
|---------------------------------------------------|-----------------|  
|**スクリプトの種類を選択します。**|このフィールドを使用して、これで使用するスクリプトの種類を選択する**Scripting** functoid。<br /><br /> 値:<br /><br /> -   **外部アセンブリ**します。 関連付ける場合、この値を使用して、 **Scripting** functoid のアセンブリをグローバル アセンブリ キャッシュ (GAC) にします。 **警告:**     外部アセンブリ内のコードは、スレッド セーフである必要があります。 ストレス条件下で、マップの複数のインスタンスを同時に実行される可能性があります。<br />-   **インライン c#** します。  関連付ける場合、この値を使用して、 **Scripting** functoid の c# コードで、**インライン スクリプト**バッファー。<br />-   **インライン JScript .NET**します。 関連付ける場合、この値を使用して、 **Scripting** JScript .NET スクリプトに functoid、**インライン スクリプト**バッファー。<br />-   **インライン Visual Basic .NET**します。 関連付ける場合、この値を使用して、 **Scripting** Visual Basic .NET コードに functoid、**インライン スクリプト**バッファー。<br />-   **インライン XSLT**します。 関連付ける場合、この値を使用して、 **Scripting** xslt に functoid、**インライン スクリプト**バッファー。<br />-   **インライン XSLT 呼び出しテンプレート**します。 関連付ける場合、この値を使用して、 **Scripting** XSLT 呼び出しテンプレート functoid、**インライン スクリプト**バッファー。|  
|**スクリプト アセンブリ**|関連付けるアセンブリを選択して、 **Scripting** functoid。 この一覧で、プロジェクトのウィンドウで参照されるアセンブリのみが表示されます。 また、GAC にアセンブリを登録する必要がありますに注意してください。<br /><br /> ときにこのフィールドは使用可能なだけ**スクリプトの種類を選択します。** に設定されている**外部アセンブリ**します。|  
|**スクリプト クラス**|このように選択したアセンブリ内のクラスを選択します。 **Scripting** functoid で使用します。<br /><br /> ときにこのフィールドは使用可能なだけ**スクリプトの種類を選択します。** に設定されている**外部アセンブリ**します。|  
|**スクリプト メソッド**|このように選択したクラス内のメソッドを選択します。 **Scripting** functoid で使用します。 **注:** メソッドで想定されている入力パラメーターの数がで指定された入力パラメーターの数と一致するかどうかを確認、**スクリプト Functoid の構成** ダイアログ ボックス。|  
|**インライン スクリプト**|書き込みまたは、このテキスト ボックスに使用するインライン スクリプトをコピーします。 有効な言語およびスクリプトは、次のとおりです。C#、JScript .NET、Visual Basic .NET、XSLT、および XSLT 呼び出しテンプレート。<br /><br /> ときにこのフィールドは使用可能なだけ**スクリプトの種類を選択します。** のいずれかに設定されている、**インライン**設定します。 **注意が必要です。** 同じメソッド シグネチャを複数回使用しないでください。 複数のスクリプト functoid には、同じメソッド シグネチャがある、BizTalk は最初の実装を選択し、他は無視されます。|  
  
 次に示しますが、どのように**Scripting** c# .Net スクリプトを使用して、電話番号を再フォーマットするマップに functoid が表示されます。  
  
 ![C を使用してマップ&#35;電話番号の書式を設定します。](../core/media/scriptingfunctoid.gif "scriptingfunctoid")  
スクリプト Functoid のマップ  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [外部アセンブリを使用するスクリプト](../core/scripting-using-external-assemblies.md)  
  
-   [インライン C#、JScript .NET、および Visual Basic .NET を使用するスクリプト](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)  
  
-   [インライン XSLT および XSLT 呼び出しテンプレートを使用するスクリプト](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)