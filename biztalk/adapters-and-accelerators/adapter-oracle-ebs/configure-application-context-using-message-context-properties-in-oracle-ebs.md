---
title: Oracle E-business Suite でのメッセージ コンテキスト プロパティを使用してアプリケーション コンテキストの構成 |Microsoft Docs
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
ms.openlocfilehash: 71920920c11028adb1f699e3faee463876399b36
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004003"
---
# <a name="configure-the-application-context-using-message-context-properties-in-oracle-e-business-suite"></a>Oracle E-business Suite でのメッセージ コンテキスト プロパティを使用してアプリケーション コンテキストを構成します。
使用して Oracle E-business Suite の成果物の操作を実行する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]アプリケーションのコンテキストを適切に設定する必要があります。 次の方法では、アプリケーションのコンテキストを設定できます。  
  
- アダプターを公開するバインドのプロパティを指定します。 詳細については、次を参照してください。[アプリケーション コンテキストの設定](../../adapters-and-accelerators/adapter-oracle-ebs/set-application-context.md)します。  
  
- アダプターを公開するメッセージ コンテキスト プロパティを使用します。 メッセージ コンテキスト プロパティを使用して、アプリケーションのコンテキストを設定するときに、次を考慮する必要があります。  
  
  -   値のみを設定する**ApplicationShortName**、**組織 Id**、 **ResponsibilityKey**、および**ResponsibilityName**を使用してメッセージ コンテキスト プロパティです。 ユーザー名とパスワードでは、バインドのプロパティを使用する必要があります。 指定された値、 **ResponsibilityKey**メッセージ コンテキスト プロパティに指定された値のオーバーライド、 **ResponsibilityName**メッセージ コンテキスト プロパティ。  
  
  -   バインドのプロパティとメッセージ コンテキスト プロパティの両方を使用して、アプリケーションのコンテキストを設定すると、メッセージ コンテキスト プロパティに指定された値は優先され、バインドのプロパティに指定された値を上書きします。 ただし、たとえば、バインドのプロパティとしてメッセージ コンテキスト プロパティとしてアプリケーションの短い名前と組織の ID および責任の名前を指定する場合、アプリケーションの短い名前の値のみから取得されます、メッセージ コンテキスト プロパティ。 残りの部分は関連するバインドのプロパティから取得されます。  
  
  アプリケーションのコンテキストを設定するプロパティをバインド経由でメッセージ コンテキスト プロパティを使用する理由 Wcf-custom 送信ポート バインドのプロパティを使用して、アプリケーションのコンテキストを設定した場合、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]特定の組織の ID、責任、およびバインドのプロパティに指定したアプリケーションに対してのみ使用できます。 反対に、メッセージ コンテキスト プロパティを使用する場合は、「汎用」の Wcf-custom 送信ポートを構成して、メッセージ レベルで、アプリケーションのコンテキストを設定します。  
  
  アダプター クライアントは、Oracle E-business Suite の操作を呼び出す Oracle E-business Suite に送信されるメッセージのメッセージ コンテキスト プロパティを設定する必要があります。 内のメッセージ[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]は変更できません。 そのため、クライアントは、まず既存のメッセージからメッセージを作成する必要があり、メッセージ コンテキスト プロパティを設定、新しいメッセージ。 このセクションで説明する手順、既存のメッセージが呼び出されることを想定して**要求**、新しいメッセージが呼び出されたと**New_Request**します。  
  
## <a name="set-the-message-context-properties-for-biztalk-applications"></a>メッセージ コンテキスト プロパティを BizTalk アプリケーションの設定します。  
  
1. BizTalk プロジェクトを開く[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。  
  
2. ソリューション エクスプ ローラーで右クリックして**参照**、 をクリックし、**参照の追加**します。  
  
3. **参照の追加**ダイアログ ボックスで、 をクリックして、**参照**タブをクリックし、場所を参照し、BizTalk プロパティ スキーマ DLL の[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]は。  
  
    この DLL`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`がインストールされている、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]で\<*インストール ドライブ*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin です。  
  
4. DLL を選択し、クリックして**追加**します。  
  
5. BizTalk オーケストレーションで、メッセージに追加する**New_Request**します。 **メッセージの種類**プロパティ、既存の要求メッセージと同じ型を選択するかどうかを確認します。  
  
6. 送信図形の前に、送信ポートに送信されるメッセージを使用してメッセージの構築図形を追加し、そのメッセージの割り当て図形中。  
  
7. 開きますメッセージの割り当て図形をダブルクリックして**BizTalk 式エディタ**します。  
  
8. **BizTalk 式エディタ**次を追加し、クリックして**OK**:  
  
   ```  
   New_Request = Request;  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ApplicationShortName) = "AR";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityKey) = "RECEIVABLES_VISION_OPERATIONS";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.ResponsibilityName) = "Receivables, Vision Operations (USA)";  
   New_Request(Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.OrganizationId) = "204";  
   ```  
  
   > [!IMPORTANT]
   >  指定された値、 **ResponsibilityKey**メッセージ コンテキスト プロパティに指定された値のオーバーライド、 **ResponsibilityName**メッセージ コンテキスト プロパティ。  
  
9. 使用して、さらに、オーケストレーションの処理は行われますかどうかを確認、 **New_Request**メッセージ。  
  
10. このオーケストレーションでを展開する前に[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]のアセンブリ参照を追加する必要があります`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`オーケストレーションを展開する BizTalk アプリケーションにします。 アセンブリを配置する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]:  
  
    1. 開始、[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理コンソール。  
  
    2. コンソール ツリーで、展開**BizTalk グループ**の順に展開**アプリケーション**、および BizTalk アセンブリを追加するアプリケーションでは、します。  
  
    3. 右クリック**リソース**、 をポイント**追加**、 をクリックし、 **BizTalk アセンブリ**します。  
  
    4. **リソースの追加**ダイアログ ボックスで、をクリックして**追加**、これは、BizTalk アセンブリ ファイルを含むフォルダーに移動します\<*インストール ドライブ*\>: \Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\bin です。 選択、`Microsoft.Adapters.OracleEBS.BiztalkPropertySchema.dll`ファイルを開き、をクリックし、**オープン**します。  
  
    5. **オプション** タブで、BizTalk アセンブリをグローバル アセンブリ キャッシュ (GAC) にインストールするためのオプションを指定し、をクリックし、 **OK**します。  
  
## <a name="set-the-language-for-performing-operations"></a>操作を実行するための言語を設定します。  
 [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]の Oracle E-business Suite では、多言語サポート (MLS) 機能をサポートし、操作を実行中に言語を指定することができます。 アダプターを公開、**言語**メッセージ コンテキスト プロパティの操作を実行するための言語を指定します。  
  
 指定された値、**言語**メッセージ コンテキスト プロパティの値を上書きする、**言語**のプロパティのバインド、 **MlsSettings**プロパティをバインドします。 詳細については、 **MlsSettings**プロパティ、バインドを参照してください[Oracle E-business Suite バインド プロパティの BizTalk アダプターについて](../../adapters-and-accelerators/adapter-oracle-ebs/read-about-the-biztalk-adapter-for-oracle-e-business-suite-binding-properties.md)します。  
  
