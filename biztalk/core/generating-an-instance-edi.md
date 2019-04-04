---
title: インスタンスの生成 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 362b9803-4d4a-4d17-9ad6-439ec4c7d8aa
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82674b175ad1c408b6ddb9f7823427a550288e96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999299"
---
# <a name="generating-an-instance-edi"></a>インスタンスの生成 (EDI)
デザイン時に、EDI スキーマからメッセージ インスタンスを生成できます。 それには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の XML ツール拡張を使用します。  
  
 完全なバッチ化されたインターチェンジ (インターチェンジ ヘッダーとグループ ヘッダーを含む) を生成することも、トランザクション セット (インターチェンジ ヘッダーとグループ ヘッダーを含まない) を生成することもできます。 完全なインターチェンジを生成する操作を実行すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、1 つのインターチェンジ ヘッダー、スキーマごとに 1 つのグループ、および各スキーマのグループごとに 3 つの同一なトランザクション セットを含むファイルが生成されます。 トランザクション セットを生成する操作を実行すると、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、1 つのトランザクション セットだけを含むファイルが生成されます。  
  
 完全なバッチ化されたインターチェンジを生成するには、バッチ スキーマに対してインスタンス生成コマンドを実行します。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によってプロジェクト内のメッセージ スキーマが検出され、それらのスキーマに対するトランザクション セットが自動的に含められます。  
  
 1 つのトランザクション セットを生成するには、メッセージ スキーマに対してインスタンス生成コマンドを実行します。 その場合、バッチ スキーマをプロジェクトに追加する必要はありません。 生成されたインスタンスにはインターチェンジ ヘッダーおよびグループ ヘッダーが含まれないので、機能 EDI インターチェンジを作成する場合はそれらを手動で追加する必要があります。  
  
 インスタンスを生成する際には、そのインスタンスで使用する構成 (区切り記号や構文識別子など) を指定するためのダイアログ ボックスが [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] に表示されます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-generate-an-instance-of-a-batched-interchange"></a>バッチ化されたインターチェンジのインスタンスを生成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。 ソリューション エクスプローラーで、プロジェクトに、メッセージ インスタンスに含めるトランザクション セットの種類ごとに 1 つのメッセージ スキーマを追加します。 エンコードの種類に応じたバッチ スキーマ (Edifact_BatchSchema.xsd または X12_BatchSchema.xsd) をプロジェクトに追加します。  
  
   > [!NOTE]
   >  バッチ スキーマは、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI フォルダーにあります。  
   > 
   > [!NOTE]
   >  インスタンスを生成する際にプロジェクトをビルドする必要はありません。  
  
2. ソリューション エクスプ ローラーで、バッチ スキーマを右クリックし、をクリックし、**プロパティ**します。  
  
3. **プロパティ**ウィンドウで、設定**インスタンスの出力の種類の生成**に**ネイティブ**または**XML**します。 選択**ネイティブ**.txt 拡張子を持つフラット ファイルの生成を求められます。 選択**XML** XML ファイルの生成を求められます。  
  
4. **出力インスタンス ファイル名**名前を入力、またはファイルを参照し、ファイルを選択します。  
  
   > [!NOTE]
   >  出力インスタンス ファイル名の値を入力しない場合、ファイル名が自動的に選択されます。 ファイル名は [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の [出力] ウィンドウに表示されます。  
   > 
   > [!NOTE]
   >  既存のファイルを選択した場合、既存のファイルの内容が、この操作によって生成された内容で置き換えられます。  
  
5. バッチ スキーマを右クリックし、をクリックし、**インスタンスの生成**します。  
  
6. **EDI インスタンスのプロパティ**ダイアログ ボックスで、クリックして、そのインスタンスで使用する区切り記号、識別子、およびその他の構成のオプション、選択**OK**します。  
  
7. 操作が成功したことを確認、**出力**ウィンドウ。  
  
8. ファイルを表示するには、キーを押して**コントロール**のリンクをクリックし、**出力**ウィンドウ。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の [BizTalk エディター] ウィンドウにファイルの内容が表示されます。  
  
   > [!NOTE]
   >  837I、837D、または 837P を含むインスタンスを生成すると、GS08 の値は誤って 00401 に設定されます。 詳細については、[EDI ソリューションで XML ツールの使用に関する既知の問題](../core/known-issues-with-xml-tools-used-with-edi-solutions.md)を参照してください。  
  
### <a name="to-generate-an-instance-of-a-transaction-set"></a>トランザクション セットのインスタンスを生成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。 インスタンスを生成するトランザクション セットの種類に応じたスキーマを追加します。  
  
   > [!NOTE]
   >  トランザクション セットのインスタンスを生成する際に、プロジェクトにバッチ スキーマを追加する必要はありません。  
  
   > [!NOTE]
   >  インスタンスを生成する際にプロジェクトをビルドする必要はありません。  
  
2. ソリューション エクスプ ローラーで、メッセージ スキーマを右クリックし、をクリックし、**プロパティ**します。  
  
3. [プロパティ] ウィンドウで次のように設定します。**インスタンスの出力の種類の生成**に**ネイティブ**または**XML**します。 選択**ネイティブ**.txt 拡張子を持つフラット ファイルの生成を求められます。 選択**XML** XML ファイルの生成を求められます。  
  
4. **出力インスタンス ファイル名**名前を入力、またはファイルを参照し、ファイルを選択します。  
  
   > [!NOTE]
   >  出力インスタンス ファイル名の値を入力しない場合、ファイル名が自動的に選択されます。 ファイル名が表示されます、**出力**のウィンドウ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
   > 
   > [!NOTE]
   >  既存のファイルを選択した場合、既存のファイルの内容が、この操作によって生成された内容で置き換えられます。  
  
5. メッセージ スキーマを右クリックし、をクリックし、**インスタンスの生成**します。  
  
6. **EDI インスタンスのプロパティ**ダイアログ ボックスで、構成オプションをクリックしたこと、選択**OK**します。  
  
7. 内のメッセージがあることを確認、**出力**操作が成功したことを示すウィンドウです。  
  
8. ファイルを表示するには、キーを押して**コントロール**出力ウィンドウ内のリンクをクリックします。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の [BizTalk エディター] ウィンドウにファイルの内容が表示されます。  
  
9. 機能 EDI メッセージを作成する場合は、テキスト エディターで、メッセージにインターチェンジ ヘッダーとグループ ヘッダーを追加します。  
  
## <a name="see-also"></a>参照  
 [デザイン時 XML ツールを使用します。](../core/using-design-time-xml-tools.md)   
 [インスタンスの検証 (EDI)](../core/validating-an-instance-edi.md)