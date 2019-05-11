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
ms.openlocfilehash: 966c0323619985766eb39611c25fe813588b4082
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394043"
---
# <a name="validating-an-instance-edi"></a>インスタンスの検証 (EDI)
デザイン時に EDI スキーマに対してインスタンスを検証することができます。 それには、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 環境で [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の XML ツール拡張を使用します。 検証するインスタンスは、1 つのトランザクション セット (インターチェンジとグループ ヘッダー) を含まない、インターチェンジ (インターチェンジとグループのヘッダーを含む)、設定の 1 つのトランザクションまたは (複数のトランザクション セットを持つ完全なバッチ化されたインターチェンジインターチェンジ ヘッダーとグループ ヘッダー)。  
  
> [!NOTE]
>  保存されたインターチェンジ XML の検証がサポートされていません。 ただし、保存されたインターチェンジを EDI の検証がサポートされています。  
  
 インスタンス検証操作では、両方の EDI および XSD 検証を実行します。  
  
 インスタンスを検証するときに[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]区切り記号や構文識別子など、そのインスタンスで検証する構成を指定するダイアログ ボックスが表示されます。  
  
## <a name="prerequisites"></a>前提条件  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理者グループのメンバーとしてログオンしている必要があります。  
  
### <a name="to-validate-an-instance-against-its-schema"></a>そのスキーマに対してインスタンスを検証するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]プロジェクトを開きます。  
  
2. ソリューション エクスプ ローラーで、メッセージ インスタンスに必要なすべてのスキーマをプロジェクトに追加します。  
  
   1. 単一のトランザクションがインターチェンジとグループ ヘッダーのないセットを検証する場合は、そのトランザクション セットのドキュメント スキーマを追加します。  
  
   2. 1 つのトランザクション セットを持つインターチェンジを検証する場合、プロジェクトを追加、そのトランザクションのスキーマとメッセージで使用するエンコードの種類に対するバッチ スキーマ (Edifact_BatchSchema.xsd または X12_BatchSchema.xsd の[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI)。  
  
      > [!NOTE]
      >  インスタンスのエンベロープを検証するには、バッチ スキーマが必要です。 メッセージ スキーマのみを使用した場合、エンベロープは検証できません。  
  
   3. 複数のトランザクション セットを持つバッチ インターチェンジを検証する場合、プロジェクトを追加、スキーマ、メッセージ インスタンスとメッセージで使用するエンコードの種類に対するバッチ スキーマ内の各トランザクション セット グループに対する (いずれかの Edifact_BatchSchema.xsd またはX12_BatchSchema.xsd [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]xsd_schema \edi にあります)。  
  
      > [!NOTE]
      >  サービス スキーマをカスタマイズしているドキュメント (トランザクション セット) スキーマにさらに、BizTalk プロジェクト内のカスタム サービス スキーマを含める必要があり、必要に応じてバッチ スキーマ。  
  
      > [!NOTE]
      >  インスタンスを検証するプロジェクトをビルドする必要はありません。  
  
3. 次のように、ソリューション エクスプ ローラーでスキーマのプロパティ ページを表示します。  
  
   1.  単一のトランザクション セットを検証する場合、そのトランザクション セットのドキュメント スキーマを右クリックし、順にクリックします**プロパティ**します。  
  
   2.  1 つのトランザクション セットを持つインターチェンジまたは複数のトランザクション セットを持つバッチ インターチェンジを検証する場合、バッチ スキーマ (Edifact_BatchSchema.xsd または X12_BatchSchema.xsd schema) を右クリックし、クリックして**プロパティ**.  
  
4. スキーマのプロパティ ウィンドウでの**入力インスタンス ファイル名**検証、または、ファイルを参照する、選択しをクリックするメッセージ インスタンスのパスと名前を入力**OK**します。  
  
5. **インスタンスの入力の種類の検証**、検証するファイルの種類を入力します。**ネイティブ**EDI ファイルまたは**XML** XML ファイル。  
  
   > [!NOTE]
   >  保存されたインターチェンジ XML の検証がサポートされていません。 XML を選択した場合、**インスタンスの入力の種類の検証**保存されたインターチェンジを検証するときにプロパティが、操作は失敗し、何が返されます。 ただし、選択した場合**ネイティブ**の**インスタンスの入力の種類の検証**保存されたインターチェンジを検証するときに、操作は成功します。  
  
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