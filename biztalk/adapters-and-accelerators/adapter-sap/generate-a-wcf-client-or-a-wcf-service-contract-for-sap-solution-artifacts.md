---
title: "WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff01e2b0-6480-427a-bc6d-6169e7d6e256
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 035f1263922a0c455662139ca112794e920e3848
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-sap-solution-artifacts"></a>WCF クライアントまたは SAP ソリューションの成果物のための WCF サービス コントラクトを生成します。
使用することができます、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは SAP アイテムの選択した操作を対象とした WCF サービス コントラクト (インターフェイス) を生成します。 ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF クライアント クラスを生成または WCF サービス コントラクト以外にも使用できます。ただし、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]標準の Microsoft Windows インターフェイスを通じて ServiceModel メタデータ ユーティリティ ツールの機能を公開します。 また、svcutil.exe ツールではない参照および検索の機能を提供し、SAP システムに接続するときに選択したバインドのプロパティに基づく構成ファイルを生成します。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用してクライアント クラスを生成する、プラグイン アダプター サービス参照の追加  
 使用して WCF クライアント クラスを生成する次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-generate-a-wcf-client-class"></a>WCF クライアント クラスを生成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでは、プロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。  
  
2.  後に、**アダプター サービス参照の追加**ダイアログ ボックスが開き、手順に従います[Visual Studio での SAP 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)SAP システムと参照操作を検索してに接続します。 選択した操作のための WCF クライアント クラスを作成することを確認**クライアント (送信操作)**からが選択されている、**選択コントラクト型**(これは、既定値) ドロップダウン リスト。  
  
3.  すべての対象をクリックする操作を選択した後**OK** WCF クライアント クラスを生成します。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 2 つのファイルをプロジェクトに追加します。  
  
-   **SAPBindingClient.cs**です。 このファイルには、生成された WCF クライアント クラスとヘルパー コード選択した操作にはが含まれています。  
  
-   **App.config**です。このファイルには、バインディング構成、およびクライアント エンドポイント構成が含まれています。 設定は、バインドとの接続の構成時に選んだ内容に基づいて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!IMPORTANT]
    >  使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しない場合はその既定値が null、プロパティのバインドが使用できないこと、app.config ファイルにします。 必要があります手動で追加するバインディングのプロパティとその値、app.config ファイルに必要な場合です。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF サービス コントラクトを生成する、プラグイン アダプター サービス参照の追加  
 使用すると、 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] SAP システムから Idoc、Rfc、および tRFCs を受信する、コードがアダプターにサービスとして機能します。 つまり、アダプターは、SAP システムから、該当するアイテムを受信して、成果物をアプリケーションに配信するようにコードで (受信) の操作を呼び出します。  
  
 アダプターからこの受信操作を受信できる WCF サービスを実装する必要があります、そのため、します。 これを行うには、使用する、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]操作用にアダプターによって公開されるサービス コントラクトを表す .NET インターフェイスを生成します。 この .NET インターフェイスは、WCF サービス コントラクトとも呼ばれます。 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]も、WCF サービスのスタブ実装を含むクラスを生成します。 操作の受信に使用できる、WCF サービスを作成するには、このインターフェイスを実装します。  
  
 使用して WCF サービス コントラクトを生成する次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-generate-a-wcf-service-contract"></a>WCF サービス コントラクトを生成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでは、プロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。  
  
2.  後に、**アダプター サービス参照の追加**ダイアログ ボックスが開き、手順に従います[Visual Studio での SAP 操作のメタデータを取得](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)SAP システムと参照操作を検索してに接続します。 選択した操作のための WCF サービス コントラクトを作成することを確認**サービス (入力方向の操作)**からが選択されている、**選択コントラクト型**ドロップダウン リスト。  
  
3.  すべての対象をクリックする操作を選択した後**OK**を WCF サービス コントラクトを生成します。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 3 つのファイルをプロジェクトに追加します。  
  
-   **SAPBindingInterface.cs**です。 このファイルには、生成された WCF サービス コントラクト (インターフェイス) と選択した操作のためのヘルパー コード。  
  
-   **SAPBindingService.cs**です。 このファイルには、スタブ SAPBindingInterface.cs で定義されているインターフェイスを実装する WCF サービス クラスが含まれています。 このクラスのメソッド内で直接 RFC、tRFC、IDOC を処理するビジネス ロジックを実装することができます。  
  
-   **App.config**です。このファイルには、バインド構成、エンドポイント動作、およびバインドとの接続の構成時に選んだ内容に基づくサービスのエンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!IMPORTANT]
    >  使用しているときに、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]文字列型のバインド プロパティの値を指定しない場合はその既定値が null、プロパティのバインドが使用できないこと、app.config ファイルにします。 必要があります手動で追加するバインディングのプロパティとその値、app.config ファイルに必要な場合です。  
  
> [!NOTE]
>  URI の接続を構成するときに、RFC サーバー パラメーターを指定する必要はありませんの[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]を WCF サービス コントラクトを生成します。 [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]クライアント接続を介して SAP システムからメタデータを取得します。  
  
## <a name="generate-a-wcf-client-class-or-a-wcf-service-contract-by-using-svcutilexe"></a>Svcutil.exe を使用して、WCF クライアント クラスまたは WCF サービス コントラクトを生成します。  
 Svcutil.exe を使用して、アプリケーションの WCF クライアント クラスまたは WCF サービス コントラクトを生成することができます。 と共に使用する svcutil.exe を構成する必要があります、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]です。 構成およびで svcutil.exe を使用の詳細については、[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]を参照してください[BizTalk adapter 用 mySAP Business Suite、ServiceModel メタデータ ユーティリティ ツールを使用して](../../adapters-and-accelerators/adapter-sap/use-the-servicemodel-metadata-utility-with-the-sap-adapter-in-biztalk.md)です。  
  
 Svcutil.exe は、出力ファイルには、WCF クライアント クラスまたは WCF サービス コントラクトを生成します。 既定のファイル名は、output.cs です。 このファイルを手動で含める必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。  
  
## <a name="see-also"></a>参照  
[WCF チャネル モデルを使用して SAP アプリケーションを開発します。](../../adapters-and-accelerators/adapter-sap/develop-sap-applications-using-the-wcf-channel-model.md)