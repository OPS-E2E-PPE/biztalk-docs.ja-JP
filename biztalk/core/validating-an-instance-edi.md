---
title: インスタンスの検証 (EDI) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e0fe4e87-5ab4-41e4-8ceb-8f6cf40cae0b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58150705b504193a527be729028b00d4384325d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993939"
---
# <a name="validating-an-instance-edi"></a>インスタンスの検証 (EDI)
デザイン時にインスタンスを EDI スキーマに対して検証することができます。 それには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の XML ツール拡張を使用します。 検証するインスタンスは、単一のトランザクション セット (インターチェンジとグループ ヘッダーなし)、単一のトランザクション セットを持つインターチェンジ (インターチェンジとグループ ヘッダーあり)、複数のトランザクション セットを持つ完全なバッチ処理されたインターチェンジ (インターチェンジとグループ ヘッダーあり) のいずれかです。  
  
> [!NOTE]
>  XML に保存されたインターチェンジの検証はサポートされていません。 しかし、EDI に保存されたインターチェンジの検証はサポートされます。  
  
 インスタンス検証操作は、EDI と XSD の検証を行います。  
  
 インスタンスを検証するとき、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、区切り記号や構文識別子など、そのインスタンスの中で検証する構成を指定するダイアログ ボックスが表示されます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-validate-an-instance-against-its-schema"></a>インスタンスをスキーマに対して検証するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。  
  
2. ソリューション エクスプローラーで、メッセージ インスタンスに必要なすべてのスキーマをプロジェクトに追加します。  
  
   1. インターチェンジやグループ ヘッダーを持たない単一のトランザクション セットを検証するときは、そのトランザクション セットのドキュメント スキーマを追加します。  
  
   2. 単一のトランザクション セットを持つインターチェンジを検証するときは、そのトランザクションのスキーマと、メッセージで使用するエンコードの種類に対するバッチ スキーマ ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 内の Edifact_BatchSchema.xsd または X12_BatchSchema.xsd のどちらか) をプロジェクトに追加します。  
  
      > [!NOTE]
      >  インスタンスのエンベロープを検証するには、バッチ スキーマが必要です。 メッセージ スキーマのみを使用する場合、エンベロープは検証されません。  
  
   3. 複数のトランザクション セットを持つバッチ インターチェンジを検証するときは、メッセージ インスタンス中の各トランザクション セット グループに対するスキーマと、メッセージで使用するエンコードの種類に対するバッチ スキーマ ([!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI 内の Edifact_BatchSchema.xsd または X12_BatchSchema.xsd のどちらか) をプロジェクトに追加します。  
  
      > [!NOTE]
      >  サービス スキーマをカスタマイズした場合は、ドキュメント (トランザクション セット) スキーマと、必要に応じてバッチ スキーマに加え、カスタム サービス スキーマを BizTalk プロジェクトに追加します。  
  
      > [!NOTE]
      >  インスタンスを検証するためにプロジェクトをビルドする必要はありません。  
  
3. 以下のようにして、ソリューション エクスプローラーでスキーマのプロパティ ページを表示します。  
  
   1.  単一のトランザクション セットを検証する場合、そのトランザクション セットのドキュメント スキーマを右クリックし、順にクリックします**プロパティ**します。  
  
   2.  1 つのトランザクション セットを持つインターチェンジまたは複数のトランザクション セットを持つバッチ インターチェンジを検証する場合、バッチ スキーマ (Edifact_BatchSchema.xsd または X12_BatchSchema.xsd schema) を右クリックし、クリックして**プロパティ**.  
  
4. スキーマのプロパティ ウィンドウでの**入力インスタンス ファイル名**検証、または、ファイルを参照する、選択しをクリックするメッセージ インスタンスのパスと名前を入力**OK**します。  
  
5. **インスタンスの入力の種類の検証**、検証するファイルの種類を入力:**ネイティブ**EDI ファイルのまたは**XML** XML ファイル。  
  
   > [!NOTE]
   >  XML に保存されたインターチェンジの検証はサポートされていません。 XML を選択した場合、**インスタンスの入力の種類の検証**保存されたインターチェンジを検証するときにプロパティが、操作は失敗し、何が返されます。 ただし、選択した場合**ネイティブ**の**インスタンスの入力の種類の検証**保存されたインターチェンジを検証するときに、操作は成功します。  
  
6. メッセージのスキーマ (Edifact_BatchSchema.xsd または X12_BatchSchema.xsd の 1 つのトランザクション セットを持つインターチェンジまたはバッチ インターチェンジを検証する場合) を右クリックし、をクリックし、**インスタンスの検証**です。  
  
7. **EDI インスタンスのプロパティ** ダイアログ ボックスで、次の操作を行います。  
  
   1.  インスタンスは、繰り返し区切り記号を使用する場合は、選択**繰り返し区切り記号**します。  
  
   2.  インスタンスは、末尾の区切り記号を使用する場合は、選択**はい**の**末尾の区切り記号を使用して**します。  
  
   3.  インスタンスが文字以外の設定を使用するかどうか**基本的な**、**拡張**または**Unicode**で**構文識別子**。  
  
   4.  **[OK]** をクリックします。  
  
       > [!NOTE]
       >  **EDI インスタンスのプロパティ** ダイアログ ボックスが表示されます をクリックした後、もう一度**OK**します。 そうである場合は、クリックして**OK**もう一度です。  
  
       > [!NOTE]
       >  **EDI インスタンスのプロパティ**同じログイン ユーザーに対して実行された最後のインスタンス検証操作で使用される同じ値を持つダイアログ ボックスが表示されます。  
  
8. 内のメッセージがあることを確認、**出力**操作が成功したことを示すウィンドウです。  
  
## <a name="see-also"></a>参照  
 [デザイン時 XML ツールを使用します。](../core/using-design-time-xml-tools.md)   
 [インスタンスの生成 (EDI)](../core/generating-an-instance-edi.md)