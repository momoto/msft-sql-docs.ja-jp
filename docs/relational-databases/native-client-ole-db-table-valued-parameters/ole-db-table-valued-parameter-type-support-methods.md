---
title: OLE DB テーブル値パラメーターの型のサポート (メソッド) | Microsoft Docs
ms.custom: ''
ms.date: 03/14/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (OLE DB), API support (methods)
ms.assetid: e3c2a450-8fd4-44cb-93d8-affe1b65c68e
author: MightyPen
ms.author: genemi
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 0b171d5d8dd043bc8c383adac79f73b56e25b5b9
ms.sourcegitcommit: 856e42f7d5125d094fa84390bc43048808276b57
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2019
ms.locfileid: "73761660"
---
# <a name="ole-db-table-valued-parameter-type-support-methods"></a>OLE DB テーブル値パラメーターの型のサポート (メソッド)
[!INCLUDE[appliesto-ss-asdb-asdw-pdw-md](../../includes/appliesto-ss-asdb-asdw-pdw-md.md)]

  次の OLE DB 標準メソッドでは、テーブル値パラメーターがサポートされます。  
  
|メソッド|テーブル値パラメーターのサポート|  
|------------|-------------------------------------|  
|ITableDefinitionWithConstraints:: CreateTableWithConstraints|テーブル値パラメーターの型情報がわかっており、その型情報に基づいてテーブル値パラメーターの行セット オブジェクトのインスタンスを作成する場合に使用します。<br /><br /> 詳細については、「[テーブル値パラメーターの行セットの作成](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameter-rowset-creation.md)」の「静的シナリオ」を参照してください。|  
|IOpenRowset::OpenRowset|テーブル値パラメーターの型情報がわかっておらず、サーバーから取得したメタデータ情報に基づいてテーブル値パラメーターの行セット オブジェクトのインスタンスを作成する場合に使用します。<br /><br /> 詳細については、「[テーブル値パラメーターの行セットの作成](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameter-rowset-creation.md)」の「動的なシナリオ」を参照してください。|  
|ISSCommandWithParameters::SetParameterInfo|テーブル値パラメーターのコマンド パラメーターを指定するには、コンシューマーが DBPARAMBINDINFO 構造体の *pwszName* メンバーでパラメーターの型を "table" または "DBTYPE_TABLE" として指定します。 *Ulparamsize*は ~ 0 に設定されています。 詳細については、「[テーブル値パラメーターを含むコマンドの実行](../../relational-databases/native-client-ole-db-table-valued-parameters/executing-commands-containing-table-valued-parameters.md)」の「テーブル値パラメーターの指定」を参照してください。|  
|ISSCommandWithParameters::SetParameterProperties|スキーマ名、型名、列の順序、既定の列など、テーブル値パラメーター固有のプロパティを設定します。<br /><br /> コンシューマーは、SSPARAMPROPS 構造体の *iOrdinal* でパラメーターの序数を指定します。 要求されるプロパティ セットは DBPROPSET_SQLSERVERPARAMETER です。|  
|ISSCommandWithParameters::GetParameterInfo|指定されたコマンドのすべてのパラメーターの型を取得します。<br /><br /> テーブル値パラメーターの場合、DBPARAMINFO 構造体の *wType* フィールドの型は DBTYPE_TABLE になります。 不明な長さを示すために、*ulParamSize* フィールドは ~0 に設定されます。|  
|ISSCommandWithParameters::GetParameterProperties|DBTYPE_TABLE 型のパラメーターの追加の型情報を取得します。<br /><br /> コンシューマーは、SSPARAMPROPS 構造体の *iOrdinal* メンバーでパラメーターの序数を指定します。 コンシューマーは、ISSCommandWithParameters:: SetParameterProperties の下に一覧表示されている DBPROPSET_SQLSERVERPARAMETER プロパティセット内の任意のプロパティを要求できます。<br /><br /> コンシューマーではテーブル値パラメーターの型がわからないため、プロバイダーは SSPROP_PARAM_TYPE_TYPENAME、SSPROP_PARAM_TYPE_SCHEMANAME、および SSPROP_PARAM_TYPE_CATALOGNAME に正しい値を設定する必要があります。 残りのプロパティ、SSPROP_PARAM_TABLE_DEFAULT_COLUMNS および SSPROP_PARAM_TABLE_COLUMN_SORT_ORDER の値は、既定の値になります。 コンシューマーがテーブル値パラメーターの型名を検出した後、IOpenRowset::OpenRowset を使用して、テーブル値パラメーターの名前を指定してこのテーブル値パラメーターのインスタンスを作成します。 詳細については、「[テーブル値パラメーターの型の検出](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameter-type-discovery.md)」を参照してください。|  
|IRowsetInfo:: GetProperties|テーブル値パラメーターの行セット プロパティを取得します。 コンシューマーはこれらのプロパティを使用して、バインドを最適に設定することができます。|  
|IColumnsRowset::GetColumnsRowset|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] テーブルに関するメタデータ情報を取得します。 テーブル値パラメーターの場合、この同じインターフェイスにより、次のような各列に関する詳細なメタデータ情報が提供されます。<br /><br /> DBCOLUMN_FLAGS では、DBCOLUMNFLAGS_ISNULLABLE ビットを使用して NULL 値許容を示します。<br /><br /> DBCOLUMN_ISUNIQUE では、列が ID 列かどうかを示します。<br /><br /> DBCOLUMN_COMPUTEMODE は、列が計算列かどうかを示します。|  
|IAccessor::CreateAccessor|テーブル値パラメーターの行セット オブジェクトをコマンド パラメーターにバインドするには、*wType* メンバーを DBTYPE_TABLE に設定してアクセサーを作成します。 DBOBJECT 構造体には、IID_IRowset または、*iid* メンバーのその他の有効な行セット オブジェクトのインターフェイスが含まれます。 フィールドの残りの部分は、DBTYPE_IUNKNOWN と同じように扱われます。|  
  
## <a name="see-also"></a>参照  
 [OLE DB テーブル値パラメーターの型のサポート](../../relational-databases/native-client-ole-db-table-valued-parameters/ole-db-table-valued-parameter-type-support.md)   
 [テーブル値パラメーターの行セットの作成](../../relational-databases/native-client-ole-db-table-valued-parameters/table-valued-parameter-rowset-creation.md)   
 [テーブル値パラメーターの使用 &#40;OLE DB&#41;](../../relational-databases/native-client-ole-db-how-to/use-table-valued-parameters-ole-db.md)  
  
  
