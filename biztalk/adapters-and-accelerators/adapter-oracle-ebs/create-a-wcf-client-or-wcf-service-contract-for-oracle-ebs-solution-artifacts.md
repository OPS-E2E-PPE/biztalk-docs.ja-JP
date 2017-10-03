---
title: "WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7ffd857-a177-423a-ae83-685d11b7aec6
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bc7fb7dc0df1c2cbf4c4f8b1118cba07df6c7231
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="generate-a-wcf-client-or-a-wcf-service-contract-for-oracle-e-business-suite-solution-artifacts"></a>WCF クライアントまたは Oracle E-business Suite ソリューションの成果物のための WCF サービス コントラクトを生成します。
使用することができます、 [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] WCF クライアント クラスまたは Oracle E-business Suite の成果物に選択した操作を対象とした WCF サービス コントラクト (インターフェイス) を生成します。 ServiceModel メタデータ ユーティリティ ツール (svcutil.exe) を WCF クライアント クラスを生成または WCF サービス コントラクト以外にも使用できます。ただし、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]標準の Microsoft Windows インターフェイスを通じて ServiceModel メタデータ ユーティリティ ツールの機能を公開します。 Svcutil.exe ツールではない参照および検索の機能も用意されていて、Oracle E-business Suite に接続するときに選択したバインドのプロパティに基づく構成ファイルを生成します。  
  
## <a name="generating-a-client-class-by-using-the-add-adapter-service-reference-plug-in"></a>使用してクライアント クラスを生成する、プラグイン アダプター サービス参照の追加  
 使用して WCF クライアント クラスを生成する次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-generate-a-wcf-client-class"></a>WCF クライアント クラスを生成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでは、プロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。  
  
2.  後に、**アダプター サービス参照の追加**ダイアログ ボックスが開き、手順に従います[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)Oracle E-business Suite に接続し、参照し、操作を検索します。 選択した操作のための WCF クライアント クラスを作成することを確認**クライアント (送信操作)**からが選択されている、**選択コントラクト型**(これは、既定値) ドロップダウン リスト。  
  
3.  すべての対象をクリックする操作を選択した後**OK** WCF クライアント クラスを生成します。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 2 つのファイルをプロジェクトに追加します。  
  
-   **OracleEBSBindingClient.cs**です。 このファイルには、生成された WCF クライアント クラスとヘルパー コード選択した操作にはが含まれています。  
  
-   **app.config**です。このファイルには、バインディング構成、およびクライアント エンドポイント構成が含まれています。 これらの構成は、バインドとの接続を構成したときに選んだ内容に基づいて、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!IMPORTANT]
    >  使用しているときに、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]文字列型のバインド プロパティの値を指定しない場合はその既定値が null、プロパティのバインドが使用できないこと、app.config ファイルにします。 必要があります手動で追加するバインディングのプロパティとその値、app.config ファイルに必要な場合です。  
  
## <a name="generating-a-wcf-service-contract-by-using-the-add-adapter-service-reference-plug-in"></a>使用して WCF サービス コントラクトを生成する、プラグイン アダプター サービス参照の追加  
 アダプターは、Oracle E-business Suite アダプター クライアントにメッセージを送信を有効にする受信操作を公開します。 などの操作には、WCF サービス コントラクトを生成する必要があります。 このセクションでは、アダプターによって公開されている受信操作のサービス コントラクトを生成する方法について説明します。  
  
 使用して WCF サービス コントラクトを生成する次の手順を実行、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
#### <a name="to-generate-a-wcf-service-contract-for-inbound-operations"></a>受信操作の WCF サービス コントラクトを生成するには  
  
1.  [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]ソリューション エクスプ ローラーでは、プロジェクトを右クリックし、をクリックして**アダプター サービス参照の追加**です。  
  
2.  後に、**アダプター サービス参照の追加**ダイアログ ボックスが開き、手順に従います[Visual Studio での Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)Oracle E-business Suite に接続します。 複数のバインドのプロパティと Oracle E-business Suite に接続するときに設定する URI プロパティがあります。  
  
3.  Oracle E-business Suite に接続すると、選択**サービス (入力方向の操作)**から、**選択コントラクト型**ドロップダウン リスト。  
  
4.  **カテゴリを選択**ボックスで、サービス コントラクトを生成する受信操作を参照します。 たとえば、**通知**操作、ルート ノードをクリックして (**/**) を選択**通知**から、**利用可能なカテゴリとoperations**ボックスをクリックして**追加**です。 受信操作を参照する方法については、次を参照してください。[参照、検索、および Oracle E-business Suite 操作のメタデータを取得する](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)です。  
  
5.  操作の WCF サービス コントラクトを生成する をクリックして**OK**です。  
  
 [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] 3 つのファイルをプロジェクトに追加します。  
  
-   **OracleEBSBindingInterface.cs**です。 このファイルには、生成された WCF サービス コントラクト (インターフェイス) と、受信操作のヘルパー コード。  
  
-   **OracleEBSBindingService.cs**です。 このファイルには、OracleDBBindingInterface.cs で定義されているインターフェイスを実装するクラスが含まれています。 入力方向の操作によって返されるレコードを処理するビジネス ロジックを実装することができます。  
  
-   **app.config**です。このファイルには、バインド構成、エンドポイント動作、およびバインドとの接続の構成時に選んだ内容に基づくサービスのエンドポイント構成が含まれています、[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]です。  
  
    > [!IMPORTANT]
    >  使用しているときに、[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]文字列型のバインド プロパティの値を指定しない場合はその既定値が null、プロパティのバインドが使用できないこと、app.config ファイルにします。 必要があります手動で追加するバインディングのプロパティとその値、app.config ファイルに必要な場合です。  
  
## <a name="using-svcutilexe-to-generate-a-wcf-client-class-or-a-wcf-service-contract"></a>Svcutil.exe を使用して WCF クライアント クラスまたは WCF サービス コントラクトを生成するには  
 Svcutil.exe を使用して、アプリケーションの WCF クライアント クラスまたは WCF サービスのインターフェイスを生成することができます。 と共に使用する svcutil.exe を構成する必要があります、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。  
  
 Svcutil.exe は、出力ファイルには、WCF クライアント クラスまたは WCF サービス コントラクトを生成します。 既定のファイル名は、output.cs です。 このファイルを手動で含める必要があります、[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]プロジェクト。 Svcutil.exe の詳細については、次を参照してください。 [http://go.microsoft.com/fwlink/?LinkId=139432](http://go.microsoft.com/fwlink/?LinkId=139432)です。