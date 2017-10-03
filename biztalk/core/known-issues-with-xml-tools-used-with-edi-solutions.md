---
title: "EDI ソリューションで使用される XML ツールに関する既知の問題 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03d9b361-be98-494c-b32d-03892672fef1
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88edef073bdab21213d9f1f52ec7e4424ff4e4b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="known-issues-with-xml-tools-used-with-edi-solutions"></a>EDI ソリューションで使用される XML ツールに関する既知の問題
このトピックでは、[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] の XML ツールに関する既知の問題について説明します。  
  
## <a name="validation-of-test-map-input-and-output-file-still-occurs-when-the-validate-property-is-set-to-false"></a>検証プロパティを [False] に設定しているのに TestMap の入力および出力ファイルの検証が実行される  
 TestMap の入力プロパティを設定してマップをテストするかどうかは**ネイティブ**TestMap 入力の検証と TestMap 出力の検証のプロパティに設定および**False**検証は実行されます。 これは、ネイティブ形式の入力ファイルを XML 形式に変換され、BizTalk Server はスキーマに対して XML を検証するために発生します。 入力ファイルに検証の問題がある場合は、この検証メカニズム エラーが通知されます、TestMap 入力の検証および TestMap 出力の検証プロパティ設定されていても**False**です。  
  
## <a name="length-validation-is-not-performed-on-a-data-element-in-a-generated-instance-that-is-pulled-from-an-enum-list-in-the-schema"></a>スキーマ内の enum の一覧から取得された生成済みインスタンスのデータ要素に対して、長さの検証が実行されない  
 スキーマからインスタンスが生成され、そのスキーマ内のデータ要素の列挙値が長さの要件を満たしていない場合、インスタンスの生成に、長さの要件のため後で XSD 検証が失敗するデータ要素が使用される可能性があります。 スキーマの検証では、スキーマ内の enum の一覧から取得された生成済みインスタンスの値が最小/最大長の要件を満たしているかどうかはチェックされません。  
  
## <a name="validate-schema-may-not-detect-an-invalid-transaction-set-id-code"></a>スキーマの検証時に無効なトランザクション セット ID コードが検出されない場合がある  
 [ソリューション エクスプ ローラー] ウィンドウでスキーマの検証コマンドを使用してスキーマを検証する場合に[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ルート ノードのチェックが無効なトランザクション セット ID コードを使用したルート参照ノードの最後の部分で認識されない (x12 _ の形式で\<VersionRelease > _TSID)。 スキーマのルート参照ノードに含まれる TSID が無効でも、その TSID がスキーマの ST01 要素の列挙ノードに含まれる TSID と同じであれば、スキーマの検証操作時に TSID が無効であることが検出されません。  
  
## <a name="visual-studio-must-be-restarted-to-make-an-enum-change-in-a-schema-effective-for-instance-validation"></a>インスタンスの検証でスキーマの enum の変更を有効にするためには Visual Studio を再起動する必要がある  
 スキーマ内の列挙の一覧を変更し、スキーマを保存した後でインスタンスの検証を実行すると、スキーマの最新バージョンではなく以前のバージョンに基づいて検証が実行されます。 スキーマの最新バージョンは、Visual Studio を再起動するまで使用されません。  
  
## <a name="the-edi-instance-properties-dialog-box-may-be-displayed-when-not-needed-in-the-testmap-operation"></a>TestMap 操作で、必要のないときに [EDI インスタンスのプロパティ] ダイアログ ボックスが表示されることがある  
 TestMap プロセス中に 2 回に BizTalk Server が EDI インスタンスのプロパティ ダイアログ ボックスに表示されますいったん、入力メッセージ インスタンスと出力メッセージを生成するため、区切り記号を入力するために 1 回を解釈するために必要な区切り記号を入力できるように、。インスタンス。 BizTalk Server では、EDI スキーマに対しては [EDI インスタンスのプロパティ] ダイアログ ボックスが 2 回だけ表示されますが、EDI 以外のスキーマに対しては 3 回以上表示されることがあります。 その場合は、ダイアログ ボックスを閉じてください。  
  
## <a name="validation-of-an-xml-preserved-interchange-is-not-supported"></a>XML の保存済みインターチェンジの検証がサポートされていない  
 XML を選択した場合は、保存されたインターチェンジを検証するときに、**インスタンスの入力の種類の検証**プロパティは、操作が失敗し、nothing が返されます。 ただし、選択した場合**ネイティブ**の**インスタンスの入力の種類の検証**保存されたインターチェンジを検証する場合、操作は成功します。  
  
## <a name="an-instance-generated-for-a-hipaa-278-schema-will-contain-both-request-and-response-sections"></a>HIPAA 278 スキーマに対して生成されたインスタンスに、要求セクションと応答セクションの両方が含まれる  
 HIPAA 278 スキーマは、278 要求メッセージと 278 応答メッセージの両方に使用されます。 278 スキーマに対してインスタンスの生成コマンドを使用すると、生成されるインスタンスには要求セクションと応答セクションの両方が含まれます。このインスタンスを送信しないでください。 使用できる 278 要求メッセージまたは 278 応答メッセージを作成するには、XML ツールによって生成されたインスタンスをテキスト エディターで開き、いずれかのセクションを削除します (たとえば、要求メッセージを作成する場合は応答セクションを削除します)。  
  
 要求セクションと応答セクションの両方を含む 278 メッセージに対してインスタンスの検証コマンドを実行すると、メッセージは 278 スキーマに対して正常に検証されます。  
  
## <a name="an-xml-instance-generated-from-a-278-hipaa-schema-will-fail-validation"></a>278 HIPAA スキーマから生成された XML インスタンスの検証が失敗する  
 インスタンスの生成コマンドを使用して 278 HIPAA スキーマから XML インスタンスを生成した後にインスタンスの検証コマンドを使用してそのインスタンスを検証すると、エラーが発生します。  
  
## <a name="a-native-instance-generated-from-a-837-schema-incorrectly-sets-gs08"></a>837 スキーマから生成されたネイティブ インスタンスが間違って GS08 を設定する  
 使用してネイティブ インスタンスの生成時に、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] X12_BatchSchema だけでなく、837I、837 D、または 837p スキーマ、GS08 の値を含むソリューションが 00401 が含まれます。 このインスタンスを処理する前に、スキーマのインスタンスの適切な値に GS08 の値を変更する必要があります。  次の表に、各 837 スキーマの正しい GS08 値を示します。  
  
|HIPAA スキーマ|GS08 値|  
|------------------|----------------|  
|837I|004010X096A1|  
|837D|004010X097A1|  
|837P|004010X098A1|  
  
## <a name="see-also"></a>参照  
 [EDI 処理に関する既知の問題](../core/known-issues-with-edi-processing.md)   
 [XML ツール拡張機能の使用](../core/using-the-xml-tool-extensions.md)   
 [デザイン時 XML ツールを使用します。](../core/using-design-time-xml-tools.md)