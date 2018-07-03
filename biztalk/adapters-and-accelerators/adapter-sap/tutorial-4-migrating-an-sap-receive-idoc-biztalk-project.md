---
title: 'チュートリアル 4: 移行を SAP IDOC 受信 BizTalk プロジェクト |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, SAP Receive IDOC BizTalk project
- migrating, SAP Receive IDOC BizTalk project
- migration
ms.assetid: 74b667d8-2d8c-4c15-9dd2-f13521404b85
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e943c3663767d2b684b0f4657f639d752705b86f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011259"
---
# <a name="tutorial-4-migrating-an-sap-receive-idoc-biztalk-project"></a>チュートリアル 4: 移行を SAP IDOC 受信 BizTalk プロジェクト
WCF ベースの Microsoft BizTalk Server に同梱されている SAP アダプターの以前のバージョンとは異なる[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]など、多くの点で。  
  
- BizTalk プロジェクトの作成、デザイン時エクスペリエンス。  
  
- メタデータの取得エクスペリエンス。  
  
- スキーマ ファイル名と名前空間。  
  
- データ型のマッピング。  
  
- アダプターを使用して実行できる操作。  
  
- BizTalk Server 管理コンソールで物理ポートの構成。  
  
  これらの相違点については、トピックで[を移行する BizTalk プロジェクト作成を使用して、前のバージョン、SAP アダプターの](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)します。  
  
  ただし、アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトに変更を加えるし、WCF ベースと連携させるため[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
  このチュートリアルでは、アダプターの以前のバージョンを使用して作成された既存の BizTalk プロジェクトにする必要があります変更について説明します。  
  
> [!NOTE]
>  説明を簡潔にするため、このチュートリアルでは SAP アダプターの以前のバージョンを vPrev SAP アダプターとして指す場合は。 同様に、vPrev SAP アダプターを使用する BizTalk プロジェクトは vPrev BizTalk プロジェクトに参照されます。  
  
## <a name="sample-used-for-the-tutorial"></a>このチュートリアルで使用されるサンプル  
 このチュートリアルは、SAP システムからフラット ファイル IDOC を受信する vPrev BizTalk プロジェクトを移行する方法を示すサンプル (ReceiveIDOC_Migration) に基づいています。 サンプルが付属、[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]します。 詳細については、次を参照してください。[アダプタ サンプル](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   VPrev BizTalk プロジェクトが必要です。 このチュートリアルには、SAP システムから ORDERS03 IDOC を受信する BizTalk プロジェクトが含まれます。  
  
-   [厳密な名前のキー ファイルの作成と、ツールの説明](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)

  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>アダプターの以前のバージョンを使用して作成された BizTalk プロジェクトを理解します。  
 IDOC を受信する vPrev BizTalk プロジェクトの主要な構成要素は次のとおりです。  
  
-   **BizTalk オーケストレーション**します。 これは、単純な SAP で構成されるオーケストレーションの受信フラット ファイル IDOC を SAP システムから受信するポート。 BizTalk プロジェクトには、オーケストレーションで使用できるように、XML、フラット ファイル IDOC に変換するフラット ファイル逆アセンブラーが含まれています。 で XML IDOC を file ポート経由のファイルの場所にコピーすると、前に、フラット ファイル アセンブラーを使用してフラット ファイル IDOC に変換されます。  
  
-   **SAP システムに送信する IDOC のスキーマ**します。 このチュートリアルには、SAP システムから ORDERS03 IDOC を受信する BizTalk プロジェクトが含まれます。 IDOC に対して生成されたスキーマは、ORDERS03.xsd です。 VPrev SAP アダプターを使用して、このスキーマが生成されます。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>BizTalk プロジェクトを移行する方法は、アダプターの以前のバージョンを使用して作成されました。  
 この移行のチュートリアルの目的は、vPrev SAP アダプターの送信ポートではなく Wcf-custom 送信ポートを使用して SAP システムからフラット ファイル IDOC を受信するためです。 どのような設定は、Wcf-custom 送信ポートに必要な詳細については、前に、まず vPrev 送信 IDOC のオーケストレーションに必要などのような物理ポートを理解する必要があります。  
  
- VPrev SAP では、SAP システムからフラット ファイル IDOC を受信するポートを受信します。 ポートもこれに変換が使用可能なフラット ファイル逆アセンブラーを使用して XML IDOC vPrev BizTalk アプリケーションの一部として。 XML の IDOC は vPrev SAP アダプターを使用して作成されたスキーマ (ORDERS03.xsd) に準拠しています。  
  
- IDOC をフォルダーにコピーする file 送信ポート。 また、このポートは、XML IDOC をフラット ファイル IDOC に変換するのに BizTalk アプリケーションで使用可能なフラット ファイル アセンブラー パイプラインを使用します。  
  
  既存の vPrev BizTalk プロジェクトを移行するには、フラット ファイル IDOC をフォルダーにコピーする file 送信ポートを変更する必要はありません。 新しい構成するだけで済みます Wcf-custom 受信ポートを適切な構成設定を使用します。 このチュートリアルは、Wcf-custom を構成する方法を示します受信 WCF ベースを使用して SAP システムから Idoc を受信するポート[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [手順 1: IDOC を受信するための vPrev BizTalk プロジェクトを構築して展開する](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc.md)  
  
-   [手順 2: WCF-Custom の一方向の受信ポートを構成する](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)  
  
-   [手順 3: 移行されたアプリケーションをテストする](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)  
  
## <a name="see-also"></a>参照  
 [SAP アダプター チュートリアル](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)