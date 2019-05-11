---
title: EDI ソリューションで使用される XML ツールに関する既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 03d9b361-be98-494c-b32d-03892672fef1
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46114bc6afdf4ed1f834dfe974439222b98ac9b8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329953"
---
# <a name="known-issues-with-xml-tools-used-with-edi-solutions"></a>EDI ソリューションで使用される XML ツールに関する既知の問題
このトピックでは、BizTalk Server の XML ツールに関する既知の問題について説明します。  
  
## <a name="validation-of-test-map-input-and-output-file-still-occurs-when-the-validate-property-is-set-to-false"></a>テスト マップ入力と出力ファイルの検証が引き続き発生時に、検証プロパティを False に設定  
 TestMap の入力プロパティを設定してマップをテストするかどうかは**ネイティブ**TestMap 入力の検証と TestMap 出力の検証のプロパティに設定し、 **False**検証は実行されます。 これは、ネイティブ形式の入力ファイルは、XML 形式に変換して、BizTalk Server は、スキーマに対して XML を検証するために発生します。 TestMap 入力の検証"と"TestMap 出力の検証プロパティ設定されていても、入力ファイルに検証の問題がある場合は、この検証メカニズムによってエラーが通知は**False**します。  
  
## <a name="length-validation-is-not-performed-on-a-data-element-in-a-generated-instance-that-is-pulled-from-an-enum-list-in-the-schema"></a>スキーマ内の enum の一覧から取得された生成済みインスタンスのデータ要素の長さの検証は実行されません。  
 インスタンスは、スキーマから生成され、スキーマ内のデータ要素の列挙値の長さの要件を満たしていない、ときに長さ要件を満たすのための XSD 検証が失敗、その後のデータ要素と、インスタンスが生成されます。 スキーマ検証では、スキーマ内の enum の一覧から取得された生成済みのインスタンスの値が、最小/最大長の要件を満たすかどうかは確認されません。  
  
## <a name="validate-schema-may-not-detect-an-invalid-transaction-set-id-code"></a>検証スキーマが無効なトランザクション セット ID コード認識されません。  
 [ソリューション エクスプ ローラー] ウィンドウでスキーマの検証コマンドを使用してスキーマを検証する[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]、ルート ノードのチェックが無効なトランザクション セット ID コードをルート参照ノードの最後の部分で認識されない (x12 _ の形式で\<VersionRelease\>_TSID)。 スキーマのルート参照ノードに含まれる TSID が有効ですが、これは、スキーマの ST01 要素の列挙ノードに含まれる TSID と同じ場合、スキーマの検証操作には TSID が無効であるは検出されません。  
  
## <a name="visual-studio-must-be-restarted-to-make-an-enum-change-in-a-schema-effective-for-instance-validation"></a>インスタンスの検証の有効なスキーマの変更列挙型を visual Studio を再起動する必要があります。  
 スキーマ内の列挙リストを変更、スキーマ、保存、インスタンスの検証を実行すると、BizTalk Server は、以前のバージョンの最新バージョンではなく、スキーマに基づいて検証を実行します。 Visual Studio を再起動するまで、BizTalk Server は、スキーマの最新バージョンを使用しません。  
  
## <a name="the-edi-instance-properties-dialog-box-may-be-displayed-when-not-needed-in-the-testmap-operation"></a>TestMap 操作で必要ない場合に、EDI インスタンスのプロパティ ダイアログ ボックスが表示される可能性があります。  
 BizTalk Server は、TestMap プロセス中に 2 回、[EDI インスタンスのプロパティ] ダイアログ ボックスを表示: したら、入力メッセージ インスタンスと出力メッセージを生成するため、区切り記号を入力するための解釈に必要な区切り記号を入力できるように、インスタンス。 BizTalk Server が EDI インスタンスのプロパティ ダイアログ ボックスと EDI スキーマ; に対して 2 回だけを表示する必要があります。ただし、BizTalk Server が、EDI スキーマ以外のダイアログ ボックスが表示され、以上可能性があります 2 回クリックします。 そうである場合は、ダイアログ ボックスを閉じます。  
  
## <a name="validation-of-an-xml-preserved-interchange-is-not-supported"></a>保存されたインターチェンジ XML の検証はサポートされていません  
 XML を選択した場合は、保存されたインターチェンジを検証するときに、**インスタンスの入力の種類の検証**プロパティは、操作は失敗し、何が返されます。 ただし、選択した場合**ネイティブ**の**インスタンスの入力の種類の検証**保存されたインターチェンジを検証するときに、操作は成功します。  
  
## <a name="an-instance-generated-for-a-hipaa-278-schema-will-contain-both-request-and-response-sections"></a>HIPAA 278 に対して生成されたインスタンス両方のスキーマが含まれる要求と応答セクション  
 HIPAA 278 スキーマは、両方 278 要求メッセージと 278 応答メッセージに使用されます。 278 スキーマに対してインスタンスの生成コマンドを使用する場合に生成されたインスタンスが送信されない要求と応答の両方のセクションになります。 使用できる 278 要求または 278 応答メッセージを作成するには、XML ツールをテキスト エディターで生成したインスタンスなどのセクションでは、1 つ削除要求メッセージの応答のセクションを削除します。  
  
 要求と応答の両方のセクションを含む 278 メッセージで、インスタンスの検証コマンドを実行する場合、278 スキーマに対してメッセージが正常に検証されます。  
  
## <a name="an-xml-instance-generated-from-a-278-hipaa-schema-will-fail-validation"></a>278 HIPAA スキーマから生成された XML インスタンスは検証に失敗します。  
 278 HIPAA スキーマから XML インスタンスを生成し、そのインスタンスを検証するインスタンスの検証コマンドを使用するインスタンスの生成コマンドを使用する場合、BizTalk Server はエラーを送信します。  
  
## <a name="a-native-instance-generated-from-a-837-schema-incorrectly-sets-gs08"></a>837 スキーマからは誤って生成されたネイティブ インスタンス GS08 を設定します。  
 使用してネイティブのインスタンスを生成するときに、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]と共に X12_BatchSchema を 837I、837 D、または 837p スキーマなど、GS08 の値を含むソリューションが 00401 が含まれます。 このインスタンスを処理する前に、スキーマのインスタンスの正しい値に GS08 の値を変更する必要があります。  次の表には、各 837 スキーマの正しい GS08 値が含まれています。  
  
|HIPAA スキーマ|GS08 値|  
|------------------|----------------|  
|837I|004010X096A1|  
|837 D|004010X097A1|  
|837 P|004010X098A1|  
  
## <a name="see-also"></a>参照  
 [EDI の処理に関する既知の問題](../core/known-issues-with-edi-processing.md)   
 [XML ツール拡張機能の使用](../core/using-the-xml-tool-extensions.md)   
 [デザイン時 XML ツールを使用します。](../core/using-design-time-xml-tools.md)