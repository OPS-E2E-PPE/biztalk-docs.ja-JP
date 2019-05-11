---
title: WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff01e2b0-6480-427a-bc6d-6169e7d6e256
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d84258ab9c1d2716f74e5bab2b4f82fd7caf11e3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373413"
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts"></a>WCF クライアントまたは SAP ソリューションの成果物の WCF サービス コントラクトを生成します。
使用することができます、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは SAP アイテムを選択した操作を対象とした WCF サービス コントラクト (インターフェイス) を生成します。 ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF クライアント クラスを生成または WCF サービス コントラクトを使用することもできます。ただし、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]標準の Microsoft Windows インターフェイスから ServiceModel メタデータ ユーティリティ ツールの機能を公開します。 Svcutil.exe ツールを使用できない参照および検索の機能を提供し、SAP システムに接続するときに選択したバインドのプロパティに基づいて構成ファイルを生成します。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>クライアント クラスの生成を使用して、プラグインのアダプター サービス参照の追加  
 使用して WCF クライアント クラスを生成する、次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-generate-a-wcf-client-class"></a>WCF クライアント クラスを生成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーが、プロジェクトを右クリックし、クリックして**アダプター サービス参照の追加**します。  
  
2. 後に、**アダプター サービス参照の追加** ダイアログ ボックスが表示されます、次の手順では、 [Visual Studio で SAP 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)SAP システムと参照と検索操作のために接続します。 選択した操作のための WCF クライアント クラスを作成することを確認します**クライアント (送信操作)** からが選択されている、**コントラクト型を選択します**(これは、既定値) のドロップダウン リスト。  
  
3. すべてのターゲット をクリックする操作を選択した後**OK** WCF クライアント クラスを生成します。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]をプロジェクトに 2 つのファイルを追加します。  
  
- **SAPBindingClient.cs**します。 このファイルには、生成された WCF クライアント クラスとヘルパーのコード選択した操作にはが含まれています。  
  
- **App.config**します。このファイルには、バインド構成とクライアント エンドポイント構成が含まれています。 バインドとの接続を構成したときに選択した内容に基づいて、設定、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
  > [!IMPORTANT]
  >  使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値が null し、プロパティのバインドが使用できないこと、app.config ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、app.config ファイルで必要な場合。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF サービス コントラクトを生成する、プラグインのアダプター サービス参照の追加  
 使用すると、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから Idoc、Rfc、Trfc を受信するには、コードがアダプターにサービスとして機能します。 つまり、アダプターは、SAP システムから、該当するアイテムを受信し、成果物をアプリケーションに配信するお客様はコードに (受信) の操作を呼び出します。  
  
 そのため、アダプターからこの受信操作を受信できる WCF サービスを実装する必要があります。 これを行うには、使用する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]操作用のアダプターによって表示されるサービス コントラクトを表す .NET インターフェイスを生成します。 この .NET インターフェイスは、WCF サービス コントラクトとも呼ばれます。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]も、WCF サービスのスタブ実装を含むクラスを生成します。 操作を受信するために使用できる WCF サービスを作成するには、このインターフェイスを実装します。  
  
 使用して WCF サービス コントラクトを生成する次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
#### <a name="to-generate-a-wcf-service-contract"></a>WCF サービス コントラクトを生成するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーが、プロジェクトを右クリックし、クリックして**アダプター サービス参照の追加**します。  
  
2. 後に、**アダプター サービス参照の追加** ダイアログ ボックスが表示されます、次の手順では、 [Visual Studio で SAP 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)SAP システムと参照と検索操作のために接続します。 選択した操作のための WCF サービス コントラクトを作成することを確認します**サービス (受信操作)** からが選択されている、**コントラクト型を選択します**ドロップダウン リスト。  
  
3. すべてのターゲット をクリックする操作を選択した後**OK**を WCF サービス コントラクトを生成します。  
  
   [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 3 つのファイルをプロジェクトに追加します。  
  
- **SAPBindingInterface.cs**します。 このファイルには、生成された WCF サービス コントラクト (インターフェイス) と選択した操作のためのヘルパー コード。  
  
- **SAPBindingService.cs**します。 このファイルには、スタブ SAPBindingInterface.cs で定義されているインターフェイスを実装する WCF サービス クラスが含まれています。 このクラスのメソッドに直接 RFC、tRFC または IDOC を処理するビジネス ロジックを実装することができます。  
  
- **App.config**します。このファイルには、バインド構成、エンドポイントの動作、およびバインドとの接続を構成したときに選択した内容に基づくサービス エンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]します。  
  
  > [!IMPORTANT]
  >  使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しないし、既定値が null し、プロパティのバインドが使用できないこと、app.config ファイルの場合は、します。 必要があります手動で追加するバインドのプロパティとその値、app.config ファイルで必要な場合。  
  
> [!NOTE]
>  接続 URI を構成するときに、RFC サーバー パラメーターを指定する必要はありませんの[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を WCF サービス コントラクトを生成します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]クライアント接続での SAP システムからメタデータを取得します。  
  
## <a name="generate-a-wcf-client-class-or-a-wcf-service-contract-by-using-svcutilexe"></a>Svcutil.exe を使用して WCF クライアント クラスまたは WCF サービス コントラクトを生成します。  
 Svcutil.exe を使用して、アプリケーションの WCF クライアント クラスまたは WCF サービス コントラクトを生成することができます。 Svcutil.exe を使用すればを構成する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。 構成と使用を svcutil.exe の詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[ServiceModel メタデータ ユーティリティ ツールを BizTalk adapter for mySAP Business Suite を使用して](../../adapters-and-accelerators/adapter-sap/use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md)します。  
  
 Svcutil.exe は、出力ファイルで、WCF クライアント クラスまたは WCF サービス コントラクトを生成します。 既定のファイル名は、output.cs です。 このファイルを手動で含める必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用して SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)