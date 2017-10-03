---
title: "BizTalk アプリケーション デザインの国際化に関する考慮事項 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9daaaaf7-6149-4e62-9e9b-b6356fc820d2
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94c1c3c6430b049d98444349394eff05eeb21561
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="international-considerations-for-designing-biztalk-applications"></a>BizTalk アプリケーション デザインの国際化に関する考慮事項
国際化対応の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] アプリケーションを開発する際には、次に挙げる既知の問題を確認することを強くお勧めします。  
  
 **コンピューター名の文字制限**  
  
 名前にアルファベット (A ～ Z、a ～ z)、数字 (0 ～ 9)、ハイフン (-)、およびアンダースコア (_) 以外の文字を含むコンピューターに [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールすることはできません。 これらの文字で指定されたコンピューター名しかサポートされません。  
  
 **文字が正しく表示されないか、不適切なフォント、フォント フォールバック設定により、まったく表示されません。**  
  
 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でホストされる [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ツールで文字 (チェコ語の文字など) を表示する際に問題が発生することがあります。 このような問題に対処するためには、Visual Studio の [オプション] タブで使用できるフォント設定を変更し、該当の文字をサポートすることがわかっている別のフォントを選択する必要があります。 フォント フォールバック機能が提供されている既定のフォントとして Tahoma または Microsoft Sans Serif を選択できます。  
  
 **サロゲート ペア文字四角形として表示では、BizTalk Server 管理コンソールおよびその他の BizTalk Server ツール**  
  
 BizTalk Server 管理コンソールおよびその他の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ツールでは、サロゲート ペアとなっている文字を表示できないことがあります。 サロゲート ペアは、2 つのコード単位で構成される 1 つの抽象文字を表すコード化文字表現として定義されています。 システム (Office XP および 2003 の中国語版も含む) 上に適切なフォントがインストールされていることを確認してください。 このような機能を持つツール ([!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] など) 内でのフォント オプションの変更も必要となる場合があります。  
  
 フォント設定オプションのないその他のツール (BizTalk Server 管理コンソールなど) では、サロゲート ペア文字は四角形として表示されます。 正方形を表示する場合、文字が破損していません。それらだけを表示できません正しくフォントのサポートの不足のためです。  
  
 **Web サービスの文字に関する制限事項**  
  
 オーケストレーションを Web サービスとして公開することを計画する場合、オーケストレーション名とポート名に使用する文字の問題に直面する可能性があります。これらの名前は、Web サービス公開ウィザードで Web サービスのファイル名 (.asmx ファイル) と仮想ディレクトリに使用されるためです。 Unicode 文字を完全にサポートしているのは、Microsoft インターネット インフォメーション サービス (IIS) 7.0 (Microsoft Windows Server 2008 および Windows Vista を含む) だけです。 したがって、IIS または Windows のこれより前のバージョンを使用する場合、オーケストレーション、ポート、Web サービスおよび仮想ディレクトリの名前に使用できるのは、Windows の該当の言語バージョンがサポートする ANSI 文字のみです (たとえば、日本語の文字は Windows の英語版では使用できません)。  
  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の Web サービスのプロジェクト名も ASCII 文字に制限されます。  
  
 **別のドキュメントのエンコーディングの使用**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、XML およびフラット ファイルのドキュメントの多様なエンコードをサポートします。たとえば、UTF-16、UTF-8、簡体字中国語 GBK、簡体字中国語 GB18030 などです。  
  
 受信ドキュメントで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]など、XML ドキュメントのエンコード宣言を認識できる"\<しますか? xml バージョン =「1.0」encoding ="GB2312"? >"です。 フラット ファイル スキーマには、**コード ページ**受信フラット ファイル ドキュメントのエンコードを示すプロパティです。  
  
 送信ドキュメント、XML とフラット ファイル アセンブラーを使用して、**表せない**プロパティです。 このプロパティを指定すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] は、元の文字セットに関係なく、送信ドキュメントを指定した文字セットに変換します。 ない場合は**表せない**プロパティが設定され、XML は utf-8 プロトコルを使用して、フラット ファイルが、フラット ファイル スキーマで指定されたコード ページを使用します。  
  
 **サポートされていないコード ページから Windows コード ページへのコードの変換**  
  
 サポートされていないコード ページから Windows コード ページへのコード変換を実装するには、カスタム パイプライン コンポーネントを作成する必要があります。  
  
 **ドキュメントのエンコードのバイト順マークへの影響**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では文字エンコードを判別し、フラット ファイル メッセージと XML メッセージで異なる特定の文字エンコードでドキュメントを生成します。  
  
 **スキーマ エディターには、1 つ以上の言語でのプロパティが含まれて**  
  
 [スキーマ エディターのプロパティ] ウィンドウおよび XML ソース コードに示される XSD (XML スキーマ定義) 言語のプロパティ名は、ローカライズされていないため、すべてのローカライズ版で英語で表示されます。 その他のプロパティはローカル言語で表示されます。 たとえば、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の簡体字中国語版では、スキーマ プロパティは英語ですが、追加のプロパティは中国語で表示されます。  
  
 **フラット ファイル内のデータのロケールに依存します。**  
  
 ロケールの多くでは、XML 標準で定義された形式とは異なる形式で日付、時刻、数、通貨などのデータを表します。 たとえば、いくつかのロケールでは、小数点の区切り文字としてピリオド (.) 以外の文字を使用します。したがって、5.75 を 5,75 と表す場合があります。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、解析が正常に行われるように、日付と時刻を除く、フラット ファイルのすべてのフィールドは文字列として扱われます。 しかし、XML 検証を使用すると、スキーマの検証中に、出力される XML メッセージがエラーになります。  
  
 日付と時刻のフィールドでは、パーサーは、カスタム日付/時刻書式 (定義されている場合) を使用してフィールド値を DateTime インスタンスに解析しようと試み、XML 形式で書き出すか、日付/時刻書式が定義されていない場合には元の値を文字列として使用します。 XML 検証を使用する場合、カスタム日付/時刻書式を使用せず、フラット ファイル メッセージで使用されるフィールド値が正しい XML 日付/時刻書式でなかった場合に、出力される日付または時刻は検証エラーとなります。  
  
 フィールド値を更新して有効な XML を生成するカスタム パイプライン コンポーネントまたはマップを作成することもできます。  
  
 **BAM 定義言語のサポート**  
  
 BAM 定義 XML ファイルを展開する前に、このファイルの作成に使用した言語が展開先のコンピューターのロケール設定に一致することを確認する必要があります。 ファイルとコンピューターの設定が一致しない場合は、まず、BM.exe の実行に使用するコンピューターを再起動します。  
  
> [!NOTE]
>  ない場合は、すべての言語が同じコード ページを使用して、または 2 つの言語が含まれますうちの 1 つは英語、BAM 定義 XML ファイルは複数の言語でテキストを含めることはできません。  
  
## <a name="see-also"></a>参照  
 [パイプライン コンポーネントの文字エンコーディングを実装します。](../core/implementing-character-encoding-in-a-pipeline-component.md)   
 [逆アセンブラー パイプライン コンポーネントでのエンコードの処理](../core/handling-encoding-in-a-disassembler-pipeline-component.md)   
 [フラット ファイル逆アセンブラー パイプライン コンポーネントでの文字エン コード](../core/character-encoding-in-the-flat-file-disassembler-pipeline-component.md)   
 [フラット ファイル アセンブラー パイプライン コンポーネントでの文字エン コード](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントでの文字エン コード](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントでの文字エン コード](../core/character-encoding-in-xml-disassembler-pipeline-component.md)