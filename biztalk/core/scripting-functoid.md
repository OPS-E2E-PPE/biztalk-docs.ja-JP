---
title: "スクリプト Functoid |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scripting functoids, about Scripting functoids
- Scripting functoids
- Scripting functoids, configuring
ms.assetid: ea8353da-049b-4e0c-a700-f51708db22a3
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 822bdbc4482a7e16a7458c7c44d128967203f283
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="scripting-functoid"></a>スクリプト Functoid
**スクリプト**functoid では、実行時に使用できない機能を実行するカスタム スクリプトまたはコードを使用することができます。 たとえばを使用して実行時に .NET アセンブリを呼び出すことができます、**スクリプト**functoid と書き込み、独自の関数。  
  
 **スクリプト**functoid は、次の言語をサポートしています。  
  
-   C# .NET  
  
-   JScript .NET  
  
-   Visual Basic .NET  
  
-   XSLT (Extensible Stylesheet Language Transformations)  
  
-   XSLT 呼び出しテンプレート  
  
 もう 1 つの大きな違い現在**スクリプト**functoid と以前のバージョンは、スクリプト必要がある不要になった作成された、functoid 自体に格納されています。 代わりに、別の .NET アセンブリにスクリプトを作成して、によるアセンブリの参照、**スクリプト**プロパティです。 個別のアセンブリにスクリプトを格納すると、1 つ以上のマップで同じスクリプトを使用できます。 さらに、できる場合がありますを購入する**スクリプト**サード パーティ ベンダーから functoid アセンブリ。  
  
 使用することができます**スクリプト**functoid の BizTalk マッパーの現在のバージョンと以前のバージョンの BizTalk マッパーで作成します。 ただし、最初に Functoid を移行する必要があります。 移行する方法の詳細についての**スクリプト**functoid を参照してください[Functoid の移行](../core/migrating-functoids.md)です。  
  
 追加すると、**スクリプト**マップに functoid、functoid を使用してスクリプトを構成する必要があります。 選択した場合、**スクリプト**functoid、**スクリプト**でプロパティが有効になっている、**プロパティ**ウィンドウです。 省略記号ボタンをクリックした場合 (**.**) のこのプロパティは、ボタン、**スクリプト Functoid の構成** ダイアログ ボックスが表示されます。 または、ダブルクリック、**スクリプト**functoid です。  
  
 次の表は、このダイアログ ボックスのフィールドを示しています。  
  
|[スクリプト Functoid の構成] ダイアログ ボックスのフィールド|Description|  
|---------------------------------------------------|-----------------|  
|**スクリプトの種類を選択します。**|このフィールドで使用するスクリプトの種類の選択を使用して**スクリプト**functoid です。<br /><br /> 値:<br /><br /> -   **外部アセンブリ**です。 関連付ける場合は、この値を使用して、**スクリプト**functoid のアセンブリ、グローバル アセンブリ キャッシュ (GAC) にします。 **警告:**外部アセンブリ内のコードはスレッド セーフである必要があります。 ストレス条件下では、マップの複数のインスタンスが同時に実行される場合があります。<br />-   **インライン c#**です。  関連付ける場合は、この値を使用して、**スクリプト**functoid で c# コード、**インライン スクリプト**バッファー。<br />-   **インライン JScript .NET**です。 関連付ける場合は、この値を使用して、**スクリプト**JScript .NET スクリプトに functoid、**インライン スクリプト**バッファー。<br />-   **インライン Visual Basic .NET**です。 関連付ける場合は、この値を使用して、**スクリプト**Visual Basic .NET コードに functoid、**インライン スクリプト**バッファー。<br />-   **インライン XSLT**です。 関連付ける場合は、この値を使用して、**スクリプト**xslt に functoid、**インライン スクリプト**バッファー。<br />-   **インライン XSLT 呼び出しテンプレート**です。 関連付ける場合は、この値を使用して、**スクリプト**XSLT 呼び出しテンプレート functoid、**インライン スクリプト**バッファー。|  
|**スクリプト アセンブリ**|関連付けるアセンブリを選択して、**スクリプト**functoid です。 プロジェクト ウィンドウで参照されるアセンブリのみ、この一覧に表示されます。 また、GAC にアセンブリを登録する必要があることに注意してください。<br /><br /> このフィールドは、のみ使用可能な場合に**スクリプトの種類を選択して**に設定されている**外部アセンブリ**です。|  
|**スクリプト クラス**|このように選択したアセンブリ内のクラスを選択して**スクリプト**functoid で使用します。<br /><br /> このフィールドは、のみ使用可能な場合に**スクリプトの種類を選択して**に設定されている**外部アセンブリ**です。|  
|**スクリプト メソッド**|このように選択したクラス内のメソッドを選択して**スクリプト**functoid で使用します。 **注:**メソッドで想定されている入力パラメーターの数で指定された入力パラメーターの数が一致を確認してください、**スクリプト Functoid の構成** ダイアログ ボックス。|  
|**インライン スクリプト**|使用するインライン スクリプトをこのテキスト ボックスに書き込みまたはコピーします。 有効な言語およびスクリプトが含まれます。 c#、JScript .NET、Visual Basic .NET、XSLT、および XSLT 呼び出しテンプレート。<br /><br /> このフィールドは、のみ使用可能な場合に**スクリプトの種類を選択して**のいずれかに設定されている、**インライン**設定します。 **注意:**同じメソッド シグネチャを複数回使用を避けてください。 複数のスクリプト Functoid が同じメソッド シグネチャを持つ場合、BizTalk は、最初の実装を選択し、他の実装を無視します。|  
  
 次に示しますが、どのように**スクリプト**c# .Net スクリプトを使用して、電話番号を再フォーマットするマップに functoid が表示されます。  
  
 ![C &#35; を使用するマップ電話番号の書式を設定します。] (../core/media/scriptingfunctoid.gif "scriptingfunctoid")  
スクリプト Functoid のマップ  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [外部アセンブリを使用するスクリプト](../core/scripting-using-external-assemblies.md)  
  
-   [インライン c#、JScript .NET、および Visual Basic .NET を使用するスクリプト](../core/scripting-using-inline-csharp-jscript-net-and-visual-basic-net.md)  
  
-   [スクリプトを使用してインライン XSLT および XSLT 呼び出しテンプレート](../core/scripting-using-inline-xslt-and-xslt-call-templates.md)