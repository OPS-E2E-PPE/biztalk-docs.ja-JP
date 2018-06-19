---
title: Oracle E-business Suite でのメッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを構成する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 51b76788-5c81-4bb4-8ef6-b1439955ea97
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 89f08c50036dd070d51a8685dc4d47ceaa231737
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25962032"
---
# <a name="configure-the-application-context-using-message-context-properties-in-oracle-e-business-suite"></a>Oracle E-business Suite でのメッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを構成します。
使用して Oracle E-business Suite の成果物の操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーションのコンテキストを適切に設定する必要があります。 次のように、アプリケーションのコンテキストを設定できます。  
  
-   アダプターを公開するバインドのプロパティを指定します。 詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)です。  
  
-   アダプターを公開するメッセージ コンテキスト プロパティを使用します。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定するときに、次を考慮する必要があります。  
  
    -   値のみを設定することができます**ApplicationShortName**、 **OrganizationID**、 **ResponsibilityKey**、および**ResponsibilityName**を使用してメッセージ コンテキスト プロパティです。 ユーザー名とパスワードでは、バインドのプロパティを使用する必要があります。 指定された値、 **ResponsibilityKey**メッセージ コンテキスト プロパティに指定された値を上書きする、 **ResponsibilityName**メッセージ コンテキスト プロパティです。  
  
    -   バインドのプロパティおよびメッセージ コンテキスト プロパティの両方を使用して、アプリケーションのコンテキストを設定すると場合のメッセージ コンテキスト プロパティの指定した値が優先され、バインドのプロパティに指定された値を上書きします。 ただし、たとえば、バインドのプロパティとしてメッセージ コンテキスト プロパティとして、アプリケーションの短い名前と組織の ID および責任の名前を指定する場合のみアプリケーションの短い名前の値から取得されます、メッセージ コンテキスト プロパティ。 残りの部分は、関連するバインドのプロパティから取得されます。  
  
 バインドのアプリケーション コンテキストを設定するプロパティをメッセージ コンテキスト プロパティを使用する理由 Wcf-custom 送信ポート バインドのプロパティを使用して、アプリケーションのコンテキストを設定した場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]特定の組織の ID、責任、およびバインドのプロパティに対して指定されたアプリケーションに対してのみ使用できます。 反対に、メッセージ コンテキスト プロパティを使用する場合は、「汎用」の Wcf-custom 送信ポートを構成して、メッセージ レベルで、アプリケーションのコンテキストを設定します。  
  
 アダプターのクライアントは、Oracle E-business Suite での操作を呼び出すための Oracle E-business Suite に送信されるメッセージのメッセージ コンテキスト プロパティを設定する必要があります。 内のメッセージ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]は変更できません。 そのため、クライアントでは、最初に既存のメッセージからメッセージを作成してプロパティを設定して、メッセージ コンテキストで新しいメッセージする必要があります。 このセクションで説明する手順、既存のメッセージが呼び出されると仮定しています**要求**、新しいメッセージが呼び出されたと**New_Request**です。  
  
## <a name="set-the-message-context-properties-for-biztalk-applications"></a>メッセージに BizTalk アプリケーションのコンテキスト プロパティを設定します。  
  
1.  BizTalk プロジェクトを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。  
  
2.  ソリューション エクスプ ローラーで右クリック**参照**、クリックして**参照の追加**です。  
  
3.  **参照の追加**ダイアログ ボックスで、 をクリックして、**参照**タブをクリックし、場所を参照し、場所 BizTalk プロパティ スキーマ DLL の[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]は使用できます。  
  
     この DLL`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`がインストールされている、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]で\<*インストール ドライブ*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin です。  
  
4.  DLL を選択し、クリックして**追加**です。  
  
5.  BizTalk オーケストレーションでメッセージを追加する、 **New_Request**です。 **メッセージの種類**プロパティ、既存の要求メッセージと同じ型を選択するかどうかを確認します。  
  
6.  送信図形の前に、送信ポートに送信されるメッセージを使用してメッセージの構築図形を追加し、メッセージの割り当て図形内です。  
  
7.  開くにはメッセージの割り当て図形をダブルクリックして**BizTalk 式エディタ**です。  
  
8.  **BizTalk 式エディタ**次を追加し、クリックして**OK**:  
  
    ```  
    New_Request = Request;  
    New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ApplicationShortName) = "AR";  
    New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityKey) = "RECEIVABLES_VISION_OPERATIONS";  
    New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityName) = "Receivables, Vision Operations (USA)";  
    New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.OrganizationId) = "204";  
    ```  
  
    > [!IMPORTANT]
    >  指定された値、 **ResponsibilityKey**メッセージ コンテキスト プロパティに指定された値を上書きする、 **ResponsibilityName**メッセージ コンテキスト プロパティです。  
  
9. 使用してさらに、オーケストレーションの処理は行われますかどうかを確認、 **New_Request**メッセージ。  
  
10. このオーケストレーションでを展開する前に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]のアセンブリ参照を追加する必要があります`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`オーケストレーションを展開する BizTalk アプリケーションにします。 内のアセンブリを展開する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]:  
  
    1.  開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソールです。  
  
    2.  コンソール ツリーで  **BizTalk グループ**の順に展開**アプリケーション**、および BizTalk アセンブリを追加するアプリケーション、します。  
  
    3.  右クリック**リソース**、 をポイント**追加**、クリックして**BizTalk アセンブリ**です。  
  
    4.  **リソースの追加**ダイアログ ボックスで、をクリックして**追加**は、BizTalk アセンブリ ファイルを含むフォルダーに移動\<*インストール ドライブ*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin です。 選択、`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`ファイルを開き、をクリックして**開く**です。  
  
    5.  **オプション** タブで、BizTalk アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールするためのオプションを指定し、をクリックして**OK**です。  
  
## <a name="set-the-language-for-performing-operations"></a>操作を実行する言語を設定します。  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] Oracle E-business Suite の多言語サポート (MLS) 機能をサポートし、操作を実行中に言語を指定することができます。 アダプターを公開、**言語**メッセージ コンテキスト プロパティの操作を実行するための言語を指定します。  
  
 指定された値、**言語**メッセージ コンテキスト プロパティの値を上書きする、**言語**下にあるプロパティのバインド、 **MlsSettings**バインディング プロパティ。 詳細については、 **MlsSettings**バインディング プロパティを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターの説明を読む](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)です。  
  
