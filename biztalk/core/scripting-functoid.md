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
ms.openlocfilehash: 5b26223884bce626404586115da36ff7989ac13b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982355"
---
# <a name="scripting-functoid"></a>スクリプト Functoid
**Scripting** functoid では、実行時に使用できない機能を実行するカスタム スクリプトまたはコードを使用することができます。 たとえばを使用して実行時に .NET アセンブリを呼び出すことができます、 **Scripting** functoid および独自のカスタム関数の記述。  
  
 **Scripting** functoid は、次の言語をサポートしています。  
  
- C# .NET  
  
- JScript .NET  
  
- Visual Basic .NET  
  
- XSLT (Extensible Stylesheet Language Transformations)  
  
- XSLT 呼び出しテンプレート  
  
  もう 1 つの重要な違い現在**Scripting** functoid と以前のバージョンは、スクリプトが必要されなく作成、functoid 自体に格納されています。 別の .NET アセンブリにスクリプトを作成し、使用してアセンブリを参照する代わりに、**スクリプト**プロパティ。 個別のアセンブリにスクリプトを格納すると、1 つ以上のマップで同じスクリプトを使用できます。 またを購入することがあります**Scripting**サード パーティ ベンダーから functoid アセンブリ。  
  
  使用することができます**Scripting** functoid を BizTalk マッパーの現在のバージョンの BizTalk マッパーの以前のバージョンで作成します。 ただし、最初に Functoid を移行する必要があります。 移行する方法の詳細についての**Scripting** functoid を参照してください[Functoid の移行](../core/migrating-functoids.md)します。  
  
  追加すると、 **Scripting**マップに functoid、functoid を使用してスクリプトを構成する必要があります。 選択した場合、 **Scripting** functoid、**スクリプト**でプロパティが有効になっている、**プロパティ**ウィンドウ。 省略記号をクリックした場合 (**.**)、このプロパティのボタン、**スクリプト Functoid の構成** ダイアログ ボックスが表示されます。 または、ダブルクリック、 **Scripting** functoid。  
  
  次の表は、このダイアログ ボックスのフィールドを示しています。  
  
|[スクリプト Functoid の構成] ダイアログ ボックスのフィールド|説明|  
|---------------------------------------------------|-----------------|  
|**スクリプトの種類を選択します。**|このフィールドを使用して、これで使用するスクリプトの種類を選択する**Scripting** functoid。<br /><br /> 値:<br /><br /> -   **外部アセンブリ**します。 関連付ける場合、この値を使用して、 **Scripting** functoid のアセンブリをグローバル アセンブリ キャッシュ (GAC) にします。 **警告:** 外部アセンブリ内のコードはスレッド セーフである必要があります。 ストレス条件下では、マップの複数のインスタンスが同時に実行される場合があります。<br />-   **インライン c#** します。  関連付ける場合、この値を使用して、 **Scripting** functoid の c# コードで、**インライン スクリプト**バッファー。<br />-   **インライン JScript .NET**します。 関連付ける場合、この値を使用して、 **Scripting** JScript .NET スクリプトに functoid、**インライン スクリプト**バッファー。<br />-   **インライン Visual Basic .NET**します。 関連付ける場合、この値を使用して、 **Scripting** Visual Basic .NET コードに functoid、**インライン スクリプト**バッファー。<br />-   **インライン XSLT**します。 関連付ける場合、この値を使用して、 **Scripting** xslt に functoid、**インライン スクリプト**バッファー。<br />-   **インライン XSLT 呼び出しテンプレート**します。 関連付ける場合、この値を使用して、 **Scripting** XSLT 呼び出しテンプレート functoid、**インライン スクリプト**バッファー。|  
|**スクリプト アセンブリ**|関連付けるアセンブリを選択して、 **Scripting** functoid。 プロジェクト ウィンドウで参照されるアセンブリのみ、この一覧に表示されます。 また、GAC にアセンブリを登録する必要があることに注意してください。<br /><br /> ときにこのフィールドは使用可能なだけ**スクリプトの種類を選択します。** に設定されている**外部アセンブリ**します。|  
|**スクリプト クラス**|このように選択したアセンブリ内のクラスを選択します。 **Scripting** functoid で使用します。<br /><br /> ときにこのフィールドは使用可能なだけ**スクリプトの種類を選択します。** に設定されている**外部アセンブリ**します。|  
|**スクリプト メソッド**|このように選択したクラス内のメソッドを選択します。 **Scripting** functoid で使用します。 **注:** メソッドで想定されている入力パラメーターの数がで指定された入力パラメーターの数と一致するかどうかを確認、**スクリプト Functoid の構成** ダイアログ ボックス。|  
|**インライン スクリプト**|使用するインライン スクリプトをこのテキスト ボックスに書き込みまたはコピーします。 有効な言語およびスクリプトが含まれます。 c#、JScript .NET、Visual Basic .NET、XSLT、および XSLT 呼び出しテンプレート。<br /><br /> ときにこのフィールドは使用可能なだけ**スクリプトの種類を選択します。** のいずれかに設定されている、**インライン**設定します。 **注意:** 同じメソッド シグネチャを複数回使用を避けてください。 複数のスクリプト Functoid が同じメソッド シグネチャを持つ場合、BizTalk は、最初の実装を選択し、他の実装を無視します。|  
  
 次に示しますが、どのように**Scripting** c# .Net スクリプトを使用して、電話番号を再フォーマットするマップに functoid が表示されます。  
  
 ![C を使用してマップ&#35;電話番号の書式を設定します。](../core/media/scriptingfunctoid.gif "scriptingfunctoid")  
スクリプト Functoid のマップ  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [外部アセンブリを使用するスクリプト](../core/scripting-using-external-assemblies.md)  
  
-   [インライン C#、JScript .NET、および Visual Basic .NET を使用するスクリプト](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)  
  
-   [インライン XSLT および XSLT 呼び出しテンプレートを使用するスクリプト](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)