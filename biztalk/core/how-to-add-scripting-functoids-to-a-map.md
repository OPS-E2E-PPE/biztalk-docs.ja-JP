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
ms.openlocfilehash: 08febb4b004dac8fa6d963ce3843e9e2275467c0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387255"
---
# <a name="how-to-add-scripting-functoids-to-a-map"></a>マップにスクリプト Functoid を追加する方法
**Scripting** functoid では、実行時に使用できない機能を実行するカスタム スクリプトまたはコードを使用することができます。 使用しての実行時に COM オブジェクトを呼び出す場合など、 **Scripting** functoid と、独自のカスタム スクリプトを記述します。  
  
 概念情報については、 **Scripting** functoid を参照してください[スクリプト Functoid の](../core/scripting-functoid.md)します。  
  
### <a name="to-add-the-scripting-functoid-to-a-map-and-configure-it"></a>スクリプト functoid をマップに追加し、構成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ツールボックス active をクリックして、**高度な Functoid** functoid のカテゴリを選択するタブ。  
  
    選択したカテゴリでの高度な functoid の一覧が表示されます。  
  
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
   >  スクリプトの種類の選択内容に応じて残りのダイアログ ボックスのフィールドのさまざまなサブセットを有効または無効にするされます。  
  
6. 選択した場合**外部アセンブリ**スクリプトの種類を使用して、**アセンブリをスクリプト**、**スクリプト クラス**、および**スクリプト メソッド**ドロップダウン関連付けるアセンブリ、クラス、およびメソッドをそれぞれ選択する、その順序でリスト、 **Scripting** functoid。  
  
   > [!WARNING]
   >  外部アセンブリ内のコードは、スレッド セーフである必要があります。 ストレス条件下で、マップの複数のインスタンスを同時に実行される可能性があります。  
  
   > [!NOTE]
   >  アセンブリでは、選択した後、**スクリプト クラス**ドロップダウン リストにそのアセンブリのクラスで設定されます。 同様に、選択した後、クラス、**スクリプト メソッド**ドロップダウン リストにそのクラスのメソッドで設定されます。  
  
   > [!NOTE]
   >  **インライン スクリプト**を選択すると、テキスト ボックスが無効になっている**外部アセンブリ**スクリプトの種類。  
  
    以外の何かを選択した場合**外部アセンブリ**スクリプトの種類 (インラインの選択肢の 1 つ) を使用して、**インライン スクリプト**テキスト ボックスに、選択した言語でスクリプトを入力します。  
  
   > [!NOTE]
   >  インライン言語の選択、 **Scripting** functoid には、c# .NET、JScript.NET、Visual Basic .NET、XSLT、および XSLT 呼び出しテンプレートが含まれます。  
  
    C# を使用するスクリプトは、"using"ステートメントは許可されません。 スクリプトは、特殊な .Net クラスを使用する必要がある場合、対応するアセンブリとその依存アセンブリに追加する「参照」に、BizTalk プロジェクトと、スクリプト コードは、完全修飾名を使用する必要があります。 カルチャに応じた小文字変換を実行するスクリプトを記述する場合は次に示すよう、対応するコード フラグメントが書き込まれます。 サポートされているすべてのスクリプト言語に同様の制限が適用されます。  
  
   ```  
   string x = y.ToLower(System.Globalization.CultureInfo.CurrentCulture);  
   ```  
  
    スクリプトでは、任意のアセンブリからクラスを使用する、マップを含む BizTalk プロジェクトで、対応するアセンブリとその依存アセンブリを「参照」を追加することを確認します。  
  
   > [!NOTE]
   >  直接カスタム スクリプトを作成できますが、**インライン スクリプト**またはテキスト ボックスに、できる他の場所でスクリプトを作成およびに貼り付けます、**インライン スクリプト**テキスト ボックス。  
  
   > [!NOTE]
   >  **アセンブリをスクリプト**、**スクリプト クラス**、および**スクリプト メソッド**インライン オプションのいずれかを選択すると、ドロップダウン リストが無効になります (以外は何か**外部アセンブリ**) スクリプトの種類。  
  
   > [!IMPORTANT]
   >  最初の関数は、メインまたはプライマリ関数として扱われます場合、複数の関数を含むスクリプトを作成します。主な機能の実行時に呼び出される場合、その他の関数がのみ呼び出されます。  
  
    **[OK]** をクリックします。  
  
7. スクリプトまたは外部アセンブリに関連付けられているメソッドは、入力パラメーターを必要とする場合は、適切な数と種類の入力リンクを基本 functoid の場合と同様作成します。  
  
8. ほとんどの状況で、 **Scripting** functoid は、送信先スキーマのフィールドを設定するために使用する出力値を生成または別の functoid に入力として多くの同じ基本的な functoid の方法の操作を行います。  
  
## <a name="see-also"></a>参照  
 [マップへの高度な Functoid の追加](../core/adding-advanced-functoids-to-a-map.md)