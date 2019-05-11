---
title: BizTalk アプリケーション デザインの国際化に関する考慮事項 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9daaaaf7-6149-4e62-9e9b-b6356fc820d2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5fad9a0933409457e4f27f2f30412902f058a900
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381716"
---
# <a name="international-considerations-for-designing-biztalk-applications"></a>BizTalk アプリケーション デザインの国際化に関する考慮事項
次の国際化対応の開発時に既知の問題を確認することを強くお勧め[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]アプリケーション。  
  
 **マシン名は文字の制限**  
  
 インストールする[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]名前に次のようなセット以外の文字を含むマシンではサポートされていません。 文字 (A ~ Z、a ~ z)、数字 (0 ~ 9)、ハイフン (-)、およびアンダー スコア (_)。 このセット内の文字が含まれているコンピューター名のみがサポートされています。  
  
 **文字が正しく表示されない、または不適切なフォント、フォント フォールバック設定により、まったく表示されません。**  
  
 文字 (チェコ語の文字) などを表示する問題が発生する可能性があります、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Microsoft でホストされているツール[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。 これらの問題に対処するには、Visual Studio のオプション タブで使用できるフォント設定を変更して、文字をサポートしていることがわかっている別のフォントを選択する必要があります。 フォント フォールバック機能が提供されている既定のフォントとして Tahoma または Microsoft Sans Serif を選択できます。  
  
 **サロゲート ペア文字表示される四角形として BizTalk Server 管理コンソールおよびその他の BizTalk Server ツール**  
  
 BizTalk Server 管理コンソールで、サロゲート ペア文字を表示すること、およびその他のならない[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ツール。 サロゲート ペアは、一連の 2 つのコード単位で構成される 1 つの抽象文字のコード化文字表現です。 (Office XP および 2003 の中国語のバージョンに含まれている)、システムにインストールされている適切なフォントがあることを確認します。 このような機能を持つツールのフォント オプションを変更するために必要な場合もあります (など[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)])。  
  
 フォントの設定オプションを使用せず、他のツールでは、サロゲート ペア文字が、管理コンソールなどの四角形として表示されます。 四角形を表示する場合、文字が破損していません。これらだけ適切に表示されないフォントのサポートがないのためです。  
  
 **Web サービスの文字に関する制限事項**  
  
 Web サービスとしてのオーケストレーションの公開の場合は、Web サービスのファイル名 (.asmx ファイル) と Web サービスで仮想ディレクトリでこれらの名前が使用されるため、オーケストレーション名とポート名に使用される文字で問題が発生する可能性があります。ウィザードを発行しています。 のみ Microsoft インターネット インフォメーション サービス (IIS) 7.0 (Microsoft Windows Server 2008 および Windows Vista に付属) 完全には、Unicode 文字がサポートしています。 そのため、以前のバージョンの IIS または Windows で、オーケストレーションの名前を使用する場合、ポート、Web サービスおよび仮想ディレクトリ名含める必要があります ANSI 文字のみが Windows の言語バージョンでサポートされている (たとえば、日本語の文字はありません許可されている Windows の英語版で)。  
  
 プロジェクトで Web サービス名も注[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ASCII 文字に制限されます。  
  
 **別のドキュメントのエンコーディングの使用**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] XML とフラット ファイル ドキュメント、たとえば utf-16、utf-8、簡体字中国語 GBK、簡体字中国語 GB18030、およびなどの多様なエンコードをサポートしています。  
  
 受信ドキュメントで、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]など、XML ドキュメントのエンコード宣言が認識できる"\<ですか? xml バージョン「1.0」encoding = ="GB2312"?\>"。 フラット ファイル スキーマには、**コード ページ**受信フラット ファイル ドキュメントのエンコードを示したりするプロパティ。  
  
 送信ドキュメント、XML およびフラット ファイル アセンブラーを使用して、**ターゲット文字セット**プロパティ。 このプロパティが指定されている場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]送信ドキュメントを元に関係なく設定の指定した文字に変換します。 ない場合は**ターゲット文字セット**プロパティが設定され、XML は utf-8 プロトコルを使用して、フラット ファイル、フラット ファイル スキーマで指定されたコード ページを使用します。  
  
 **サポートされていないコード ページから Windows コード ページに、コードの変換**  
  
 サポートされていないコード ページから Windows コード ページに、コードの変換を実装するには、カスタム パイプライン コンポーネントを作成する必要があります。  
  
 **ドキュメントのエンコーディングでバイト順マークへの影響**  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 文字エンコーディングを決定し、特定の文字エンコーディングが異なるフラット ファイルと XML メッセージでドキュメントを生成します。  
  
 **スキーマ エディターは、1 つ以上の言語でのプロパティを含めることができます。**  
  
 スキーマ エディターのプロパティ ウィンドウで、XML ソース コードに示すように XML スキーマ定義言語 (XSD) のプロパティ名はローカライズされていないと、すべてのローカライズ版で英語で表示されます。 その他のプロパティは、ローカルの言語で表示されます。 たとえば、簡体字中国語バージョンので[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]スキーマのプロパティは英語が、追加のプロパティが中国語で表示されます。  
  
 **フラット ファイルのロケールに依存するデータ**  
  
 多くのロケールでは、日付、時刻、数、および、XML 標準で定義された形式のさまざまな形式を使用して通貨などのデータを表します。 たとえば、いくつかのロケールは、数 5 と 3 つの四半期を 5,75 と表すことができますので、ピリオド (.) 以外の 10 進区切り記号を使用します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、すべてのフィールドを除く、フラット ファイル日付および時間は、解析が正常に完了するため、文字列として扱われます。 ただし、XML の検証を使用する場合、結果の XML メッセージは、スキーマの検証中に失敗します。  
  
 日付と時刻のフィールドは、パーサーは、フィールドの値が定義されていると、XML 形式で書き出すまたは日付/時刻書式が定義されていない場合、文字列として、元の値を使用する場合は、カスタムの日付または時刻の形式を使用して、DateTime インスタンスの解析を試みます。 ここでも、XML の検証を使用する場合結果として得られる日付または時刻は検証エラー、カスタム日付/時刻の形式を使用しないと、フラット ファイル メッセージで使用されるフィールドの値は、正しい XML 日付または時刻の形式ではありませんでした。  
  
 カスタム パイプライン コンポーネントまたは有効な XML を生成するためにフィールドの値を更新するマップを作成できますもことに注意してください。  
  
 **BAM 定義言語のサポート**  
  
 BAM 定義 XML ファイルを展開する前に、このファイルを作成するために使用する言語が展開先のコンピューターのロケールの設定と一致することを確認する必要があります。 ファイルとコンピューターの設定が一致しない場合は、最初に、BM.exe の実行に使用するコンピューターを再起動する必要があります。  
  
> [!NOTE]
>  BAM 定義 XML ファイルは、同じコード ページを使用して、すべての言語または 2 つだけの言語が含まれます、1 つは英語でない限り、複数の言語でテキストを含めることはできません。  
  
## <a name="see-also"></a>参照  
 [パイプライン コンポーネントにおける文字エンコーディングを実装します。](../core/implementing-character-encoding-in-a-pipeline-component.md)   
 [逆アセンブラー パイプライン コンポーネントでのエンコードの処理](../core/handling-encoding-in-a-disassembler-pipeline-component.md)   
 [フラット ファイル逆アセンブラー パイプライン コンポーネントでの文字エン コード](../core/character-encoding-in-the-flat-file-disassembler-pipeline-component.md)   
 [フラット ファイル アセンブラー パイプライン コンポーネントでの文字エン コード](../core/character-encoding-in-the-flat-file-assembler-pipeline-component.md)   
 [XML アセンブラー パイプライン コンポーネントでの文字エン コード](../core/character-encoding-in-the-xml-assembler-pipeline-component.md)   
 [XML 逆アセンブラー パイプライン コンポーネントでの文字エンコード](../core/character-encoding-in-xml-disassembler-pipeline-component.md)