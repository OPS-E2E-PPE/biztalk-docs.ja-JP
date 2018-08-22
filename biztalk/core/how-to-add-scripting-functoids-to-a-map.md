---
title: マップにスクリプト Functoid を追加する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.mapper.functiod.script
ms.assetid: eb96814a-b3fb-48f6-a947-ab595a270faa
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e983564b448ef27323879c6db15ccc232d032d8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019140"
---
# <a name="how-to-add-scripting-functoids-to-a-map"></a>マップにスクリプト Functoid を追加する方法
**Scripting** functoid では、実行時に使用できない機能を実行するカスタム スクリプトまたはコードを使用することができます。 使用しての実行時に COM オブジェクトを呼び出す場合など、 **Scripting** functoid と、独自のカスタム スクリプトを記述します。  
  
 概念情報については、 **Scripting** functoid を参照してください[スクリプト Functoid の](../core/scripting-functoid.md)します。  
  
### <a name="to-add-the-scripting-functoid-to-a-map-and-configure-it"></a>マップにスクリプト Functoid を追加して構成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。  
  
    選択したカテゴリに含まれる高度な Functoid の一覧が表示されます。  
  
2. ドラッグ、 **Scripting** functoid ![](../core/media/bts-tls-scripting.gif "bts_tls_scripting")ツールボックスからグリッド ページの適切な場所にします。  
  
   > [!NOTE]
   >  Functoid は表示されているグリッド ページに配置されます。 別のグリッド ページに functoid を配置する場合は、最初にその他のグリッド ページを表示する必要があります。  
  
   > [!NOTE]
   >  まとめて 1 つ以上の functoid を使用してマップを構築する場合は、左から右の相対的な配置を考慮する必要があります。 Functoids は左から順に実行されます。 1 つの Functoid からの出力は、これよりも右にある Functoid にのみ入力することができます。  
  
3. 選択、 **Scripting** functoid は、表示されているグリッド ページに追加したとしています。  
  
4. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロパティ ウィンドウで、省略記号ボタンをクリックします (**.**) ボタンに関連付けられている、**スクリプト**プロパティ。  
  
   > [!NOTE]
   >  または、functoid を右クリックし をクリックし、 **Functoid スクリプトの構成**のコンテキスト メニュー。 **スクリプト Functoid の構成** ダイアログ ボックスが表示されます、**スクリプト Functoid の構成**タブを選択します。  
  
5. **スクリプト Functoid の構成** ダイアログ ボックスで、**スクリプトの種類を選択します。** ドロップダウン ボックスの一覧で、スクリプトの種類を選択します。  
  
   > [!NOTE]
   >  選択されるスクリプトの種類に応じて、残りのダイアログ ボックス フィールドのさまざまなサブセットが有効および無効になります。  
  
6. 選択した場合**外部アセンブリ**スクリプトの種類を使用して、**アセンブリをスクリプト**、**スクリプト クラス**、および**スクリプト メソッド**ドロップダウン関連付けるアセンブリ、クラス、およびメソッドをそれぞれ選択する、その順序でリスト、 **Scripting** functoid。  
  
   > [!WARNING]
   >  外部アセンブリのコードは、スレッド セーフであることが必要です。 ストレス条件下では、マップの複数のインスタンスが同時に実行される場合があります。  
  
   > [!NOTE]
   >  アセンブリでは、選択した後、**スクリプト クラス**ドロップダウン リストにそのアセンブリのクラスで設定されます。 同様に、選択した後、クラス、**スクリプト メソッド**ドロップダウン リストにそのクラスのメソッドで設定されます。  
  
   > [!NOTE]
   >  **インライン スクリプト**を選択すると、テキスト ボックスが無効になっている**外部アセンブリ**スクリプトの種類。  
  
    以外の何かを選択した場合**外部アセンブリ**スクリプトの種類 (インラインの選択肢の 1 つ) を使用して、**インライン スクリプト**テキスト ボックスに、選択した言語でスクリプトを入力します。  
  
   > [!NOTE]
   >  インライン言語の選択、 **Scripting** functoid には、c# .NET、JScript.NET、Visual Basic .NET、XSLT、および XSLT 呼び出しテンプレートが含まれます。  
  
    C# でスクリプトを記述する場合、"using" ステートメントは使用できません。 スクリプトで特殊な .NET クラスを使用する必要がある場合は、対応するアセンブリとその依存アセンブリを BizTalk プロジェクトの "参照" に追加し、スクリプト コードでは完全修飾名を使用してください。 カルチャに応じた小文字変換を実行するスクリプトを記述する場合は、対応する次のようなコードを記述する必要があります。 同様の制限は、サポートされるすべてのスクリプト言語に適用されます。  
  
   ```  
   string x = y.ToLower(System.Globalization.CultureInfo.CurrentCulture);  
   ```  
  
    このスクリプトでは、任意のアセンブリのクラスを使用するために、マップが含まれる BizTalk プロジェクトの "参照" に、対応するアセンブリとその依存アセンブリを追加します。  
  
   > [!NOTE]
   >  直接カスタム スクリプトを作成できますが、**インライン スクリプト**またはテキスト ボックスに、できる他の場所でスクリプトを作成およびに貼り付けます、**インライン スクリプト**テキスト ボックス。  
  
   > [!NOTE]
   >  **アセンブリをスクリプト**、**スクリプト クラス**、および**スクリプト メソッド**インライン オプションのいずれかを選択すると、ドロップダウン リストが無効になります (以外は何か**外部アセンブリ**) スクリプトの種類。  
  
   > [!IMPORTANT]
   >  複数の関数を含むスクリプトを作成すると、最初の関数がメイン関数または主要な関数として扱われます。他の関数は、主要な関数の実行時にのみ呼び出されます。  
  
    **[OK]** をクリックします。  
  
7. スクリプトまたは外部アセンブリの関連付けられているメソッドに入力パラメーターが必要な場合は、基本的な Functoid の処理と同様に、適切な数および種類の入力リンクを作成します。  
  
8. ほとんどの状況で、 **Scripting** functoid は、送信先スキーマのフィールドを設定するために使用する出力値を生成または別の functoid に入力として多くの同じ基本的な functoid の方法の操作を行います。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)